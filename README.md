# GWR_GWG
"지리적 가중 회기 분석" 또는 Geographically Weighted Regression(GWR)은 공간 데이터 분석을 위한 통계 기법 중 하나입니다. 이 방법은 전통적인 회귀 분석과는 달리, 관측값의 공간적 위치에 따라 회귀 계수가 달라질 수 있음을 인식합니다.
전통적인 회귀 모델은 전체 데이터셋에 대한 단일 회귀 계수(기울기)를 생성하지만, GWR은 데이터의 각 위치에 대해 별도의 회귀 계수를 생성합니다. 이는 공간적으로 가변적인 관계를 더 잘 설명할 수 있게 해줍니다. 
예를 들어, 주택 가격에 대한 모델을 만들 때, 도시의 다른 지역에서는 주택 가격에 영향을 미치는 요인이 다를 수 있습니다. 도시 중심부에서는 이동 편의성이 주택 가격에 큰 영향을 미칠 수 있지만, 교외 지역에서는 학군이 더 중요한 요인이 될 수 있습니다. GWR은 이러한 공간적 특성을 고려하여, 도시의 각 지역에 대한 별도의 회귀 모델을 생성합니다.
하지만 GWR도 주의해야 할 점이 있습니다. GWR 모델은 많은 수의 회귀 계수를 추정하기 때문에, 과적합의 위험이 있습니다. 따라서, 적절한 모델 검증 절차를 통해 모델의 타당성을 확인하는 것이 중요합니다.
지리적 가중 회기 분석(Geographically Weighted Regression, GWR)의 모델링 절차는 전통적인 회귀 분석과 유사하나, 몇 가지 특별한 단계가 포함됩니다. 다음은 일반적인 GWR 모델링 절차입니다:

1. **문제 정의 및 데이터 수집**: GWR을 사용하려는 연구 문제를 정의하고, 관련된 공간 데이터를 수집합니다.
2. **변수 선택**: 종속 변수와 독립 변수를 선택합니다. 이 단계에서는 통계적인 방법뿐만 아니라, 주제에 대한 이론적 지식을 활용하는 것이 중요합니다.
3. **공간 데이터의 시각화**: 공간 데이터를 시각화하여, 데이터의 분포와 패턴을 파악합니다. 이 단계는 데이터의 특성을 이해하고, 후속 분석에 필요한 통찰력을 얻는 데 도움이 됩니다.
4. **전역 회기 모델링**: 전역 회기 모델 (예: 선형 회기)을 적합하여, 변수 간의 전반적인 관계를 파악합니다.
5. **GWR 모델링**: GWR 모델을 적합하여, 공간적으로 가변적인 회기 계수를 추정합니다. 이 단계에서는 주로 거리 가중치 함수를 사용하여, 각 관측 위치에서 주변 관측치에 더 큰 가중치를 부여합니다.
6. **모델 검증**: GWR 모델의 예측력을 검증하고, 모델의 타당성을 평가합니다. 이는 과적합을 방지하고, 모델의 일반화 성능을 확인하는 데 중요합니다.
7. **결과 해석 및 통신**: 결과를 해석하고, 공간적으로 가변적인 회기 계수를 시각화하여, 연구 문제에 대한 통찰력을 제공합니다.
이러한 절차는 일반적인 가이드라인이며, 특정 연구 문제나 데이터의 특성에 따라 적절한 조정이 필요할 수 있습니다.

**공간 가중치**는 공간 데이터 분석에서 사용되는 개념으로, 특정 지점에서의 관측치가 주변 지점에 미치는 영향을 나타냅니다. 이는 "공간적 자기상관성"이라는 원칙을 반영한 것으로, 이는 가까운 것들이 멀리 있는 것들보다 더 비슷하다는 공간적 패턴의 기본적인 특성을 말합니다.
공간 가중치는 일반적으로 두 지점 사이의 거리에 기반한 함수로 계산됩니다. 거리가 멀어질수록 가중치는 감소합니다. 이런 가중치는 지리적 가중 회기 분석(Geographically Weighted Regression, GWR)과 같은 분석에서 사용되며, 특정 지점에서의 회기 계수를 추정할 때 주변 관측치에 더 큰 가중치를 부여하는 데 사용됩니다.
공간 가중치는 다양한 형태의 함수로 설정할 수 있습니다. 일반적으로 사용되는 거리 가중치 함수에는 가우스 함수, 역거리 함수 등이 있습니다. 가우스 함수는 정규 분포를 따르는 형태로 거리에 따른 가중치를 부여하며, 역거리 함수는 거리의 역수에 비례하는 가중치를 부여합니다. 이러한 함수 선택은 연구 문제와 데이터의 특성에 따라 달라질 수 있습니다.

## packages
마지막까지 두 패키지를 테스트해보았습니다. 
1. spgwr
   cran : https://cran.r-project.org/web/packages/spgwr/index.html

   장점 : sf data로 모델링 할 수 있다. sf data는 다루기 쉽다.
   단점 : model predict가 까다롭다. 모델 그리드와 예측 그리드를 동일하게 세팅했으나 실패함. 아직 이유를 찾지 못했으나 이후 버전이 1.0 이상이 되면 다시 검토해 볼 생각 

3. GWmodel
   cran : https://cran.r-project.org/web/packages/GWmodel/index.html

   장점 : model prediction 문제 해결. 그리고 sp data가 sf data에 비해 속도가 빠르다.
   단점 : sp data를 생성해야 사용할 수 있다. 사실 지금은 이게 단점인가 싶기는 하다.
   
R 언어에서는 다음과 같은 패키지를 준비합니다. 
tidyverse : 데이터 전처리와 핸들링을 위한 패키지
sf        : sf 공간 데이터를 처리하기 위한 패키지
sp        : sp 공간 데이터를 처리하기 위한 패키지
GWmodel   : GWR 모델링을 위한 패키지

```
library(tidyverse)
library(sf)
library(sp)
library(GWmodel)
```

## data
공간 데이터를 준비합니다. 일반적인 관계형 데이터에 공간 단위가 첨부된 데이터를 말합니다. 폴리곤 혹은 좌표 모두 상관 없습니다. 다만 폴리곤의 경유 센터로이드 좌표를 이용하는 것이 효율적입니다.
sf data도 상관없습니다. 이후 sp data로 변환하면 되죠.

데이터 준비 과정에서 가장 중요한 지점은 훈련 데이터의 좌표와 예측 데이터의 좌표가 동일한 차원을 가져야 한다는 것입니다. 다시 말해 훈련과 예측 데이터의 좌표가 1:1 대응이 되는 것이 가장 좋습니다. 물론 좌표의 개수를 동일하게 하고 좌표 값을 바꾼 데이터에도 적용 가능합니다. 그러나 대규모의 데이터에서 이러한 차이는 에러를 불러올 가능성이 높습니다. 모델의 범용성이 아직 확보되지 않았습니다. 따라서 실무에서는 공간단위에서 좌표의 개수와 위치 모두 1:1 대응이 되로록 데이터를 준비하는 것을 원칙으로 삼는 것이 좋을 것 같습니다.

* 표준화된 좌표집합에 데이터를 구겨 넣기 위한 코드 예시
```
GRID_GWR <- as.tibble(unique(dt_train_sales_PCA$GRID_ID))

YYYYMM_GWR <- as.tibble(as.character(unique(dt_train_sales_PCA$BS_YR_MON)))
temp <- GRID_GWR
temp_time <- YYYYMM_GWR
for( i in 1:(length(unique(dt_train_sales_PCA$BS_YR_MON))-1)){
  temp <- bind_rows(temp, GRID_GWR)
}

for( i in 1:(length(unique(dt_train_sales_PCA$GRID_ID))-1)){
  temp_time <- bind_rows(temp_time, YYYYMM_GWR)
}
GRID_GWR <- temp
YYYYMM_GWR <- temp_time

FRANE_timeGEO <- bind_cols(YYYYMM_GWR, GRID_GWR)
colnames(FRANE_timeGEO) <- c("BS_YR_MON", "GRID_ID")
```

이러한 데이터 차원의 제약은 시계열 데이터를 한 번에 처리할 수 없다는 불편함이 있습니다. 이는 모델링의 목적과 제약 사항을 설정하면서 적합한 절차를 설정해야 함을 의미합니다. 

예를 들어 한 시계열에 공간단위로 1000개의 좌표가 있다고 합시다. 시계열이 분기 단위로 4년치가 있다고 가정한다면 총 16개 기간의 시계열이 있게 됩니다. 그렇다면 각 시계열마다 1000개의 공간단위 데이터가 있을 것이므로 총 16,000개의 데이터가 있으며 각 좌표 마다 16개의 중복이 발생하게 됩니다. 이런 중복을 한 번에 처리하지 못하는 문제가 있습니다. 이를 효율적으로 처리하는 방법은 앞으로의 과제입니다.

## model
1. sf to sp
sf 공간데이터를 sp 객체로 변환합니다. 이는 GWmodel 패키지 사용에 있어 필수적인 과정입니다.
```
dt_train_sales_PCA_norm <- st_as_sf(dt_train_sales_PCA_norm)
dt_train_sales_PCA_sp <- as(dt_train_sales_PCA_norm, Class = "Spatial")
```

2. 공간가중치
공간가중치는 글로벌 모델을 만드는 과정에서 생성합니다. 이 가중치를 이용하여 모델 트레이닝을 합니다.
GWmodel 패키지는 공간가중치를 생성하면서 부트스태랩과 같은 샘플링을 통해 최적화합니다.
```
formula_gwr <- amt_sales ~ AGE_CD + mean_dist_work + RC1_income_use + RC2_pop_credit + RC3_op_shop +
                        RC4_rt_loan_risk + RC5_cls_shop

gwr_model2 <- bw.gwr(formula_gwr,
                      data = dt_train_sales_PCA_sp,
                      approach = "AIC",
                      adaptive = T,)

gwr_model2
```

1. 모델링
```
gwr_GWG2 <-gwr.basic(formula_gwr, 
                     adaptive = T,
                     data = dt_train_sales_PCA_sp,
                     bw = gwr_model2)
gwr_GWG2
```
1. predict
```
dt_test_sales_PCA_norm_sp <- st_as_sf(dt_test_sales_PCA_norm)
dt_test_sales_PCA_norm_sp <- as(dt_test_sales_PCA_norm_sp, Class = "Spatial")
gwr_pred <- gwr.predict(formula_gwr, 
                     adaptive = T,
                     data = dt_train_sales_PCA_sp,
                     predictdata = dt_test_sales_PCA_norm_sp,
                     bw = gwr_model2)
gwr_pred
```







