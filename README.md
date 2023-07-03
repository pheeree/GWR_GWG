# GWR_GWG

## packages
마지막까지 두 패키지를 테스트해보았다. 
1. spgwr
   cran : https://cran.r-project.org/web/packages/spgwr/index.html

   장점 : sf data로 모델링 할 수 있다. sf data는 다루기 쉽다.
   단점 : model predict가 까다롭다. 모델 그리드와 예측 그리드를 동일하게 세팅했으나 실패함. 아직 이유를 찾지 못했으나 이후 버전이 1.0 이상이 되면 다시 검토해 볼 생각 

3. GWmodel
   cran : https://cran.r-project.org/web/packages/GWmodel/index.html

   장점 : model prediction 문제 해결. 그리고 sp data가 sf data에 비해 속도가 빠르다.
   단점 : sp data를 생성해야 사용할 수 있다. 사실 지금은 이게 단점인가 싶기는 하다.
   
## data
