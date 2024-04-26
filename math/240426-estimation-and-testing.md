## 1\. 확률분포

**a. uniform distribution(균등분포)**

**b. normal distribution(정규분포)**

    - 표준정규분포

**c. binominal distribution(이항분포)**

    - 베르누이분포 -> 이항분포

## 2.추정(Estimation)

**a. 점추정**

**b. 구간추정**

    - 신뢰구간

## 3\. 검정(Test)

**a. 가설과 가설점정**

    - 귀무가설, 대립가설

**b. 가설검정의 오류**

    - 1종오류, 2종오류

**c. 유의수준과 유의확률**

    - p-value

**d. 검정방법**

    - 양측검정, 단측검정

**e. 검정의 절차**

    - 가설수립 -> 유의수준 결정 -> 기각역 결정 -> 통계량의 계산 -> 의사계산

**f. 대표적 검정 종류** 

    i) 표본개수 1~2개 -> t-test(단일표본, 두 종속표본, 두 독립표본) 

    ii) 표본개수 3개 이상 -> anova(일원분산분석, 이원분산분석)

        - _사전 정규성 체크_ : shapiro sp.stats.shapiro(store\[0\])

        - _사전 등분산성 체크_ : levene sp.stats.levene(store\[0\], store\[1\], store\[2\])

            - 등분산성 : anova(or equal\_val=True) pg.anova(dv\='satisfaction', between\='store', data\=df1)

            - 이분산성 : welch\_anova(or equal\_val=False) pg.welch\_anova(dv\='satisfaction', between\='store', data\=df1)

        - _사후분석_ 방법 : posthocs scikit\_posthocs.posthoc\_scheffe(df1, val\_col\='satisfaction', group\_col\='store')
