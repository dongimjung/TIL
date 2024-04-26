셀레니움과 웹드라이버 매니저 설치

```
!pip install selenium
!pip install webdriver-manager
```

필요한 모듈 import 및 브라우저 생성

```
from selenium import webdriver
from selenium.webdriver.chrome.service import Service as ChromeService
from webdriver_manager.chrome import ChromeDriverManager
from selenium.webdriver.common.by import By
browser = webdriver.Chrome(service=ChromeService(ChromeDriverManager().install()))
```

Yes24의 베스트셀러 1~3페이지의 {책이름, 저자, 출판일, 가격, 판매지수} 들을 받아서 dictionary타입에 넣어 csv파일로 추출하기.

```
data_list = []
for i in range(1,3):
    url = 'https://www.yes24.com/Product/Category/BestSeller?categoryNumber=001&pageNumber='+str(i)+'&pageSize=24'
    browser.get(url)
    container = browser.find_elements(By.CLASS_NAME, 'itemUnit') # text => 변수
    
    for elem in container:
        title = elem.find_element(By.CLASS_NAME, 'gd_name').text
        writer = elem.find_element(By.CLASS_NAME, 'info_auth').find_elements(By.TAG_NAME, 'a')[0].text
        published_at = elem.find_element(By.CLASS_NAME, 'info_date').text
        price = elem.find_element(By.CLASS_NAME, 'yes_b').text
        sale_num = elem.find_element(By.CLASS_NAME, 'saleNum').text

        print(title, writer, published_at, price, sale_num)
        data_list.append({
            "제목": title,
            "저자": writer,
            "출판일": published_at,
            "가격": price,
            "판매지수": sale_num
        })

import pandas as pd        
df = pd.DataFrame(data_list)
df.to_csv()
```

(위의 예제에서는 요소 안의 text를 가져오는 것만 있는데, 그 밖에 get\_attribute("href") 등으로 a 태그 안의 url 등 이것저것 가져올 수도 있다)

그 외에 크롤링할 때 실질적으로 필요할 만한 내용들을 많이 배웠다.

예를 들면, 어느 요소를 클릭하고(.click()) 로그인하고(.send\_keys("아이디/비번")) 엔터 누르고(이건 Keys 라이브러리 필요한듯) 이런 행동들도 가능하다.

여기부터는 김인섭 강사님의 교재를 복붙하겠다..

[##_Image|kage@kSaLS/btsGtln2Jr1/2LsIZ0wcoOLSEVDEbtwnC1/img.png|CDM|1.3|{"originWidth":727,"originHeight":461,"style":"alignLeft","filename":"스크린샷 2024-04-08 오전 12.22.13.png"}_##]
