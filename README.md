## 빅데이터 프로그래밍(N)_A팀   

### 데이터 파일 설명   
- 데이터 파일1. road.shp, road.dbf, road.shx, road.prj  
  
: 임도 데이터 파일.  
임도 위치의 좌표, 임도 폭 정보를 활용하기 위해 사용.  
   
원본 데이터명: 임도망도(국유림)    
설명: 국유림 내 임도(산림도로)의 위치, 속성, 공간 분포 정보    
제공기관: 산림공간정보 서비스   
파일 형식: 복수 파일로 구성  
구성 파일:  
road.shp – 공간 데이터 (선형 정보)   
road.dbf – 속성 테이블   
road.shx – 인덱스   
road.prj – 좌표계 정보   
출처: https://map.forest.go.kr/forest/?systype=mapSearch&searchOption=imdo   
<br>    
     
- 데이터 파일2. fire.csv   
  
: 산불 데이터 파일        
산불 발생 지점과 산불 원인 정보를 활용하기 위해 사용.

: API 호출 직후, 가공 없이 저장한 원시 데이터  
    
원본 데이터명: 산림청_산불통계   
설명: 지역, 원인, 시기별 산불 발생 및 진화 현황에 대한 통계 자료   
제공기관: 산림청 (공공 데이터 포털 OpenAPI 제공)   
API 유형: REST API   
파일 형식: XML   
출처: https://www.data.go.kr/tcs/dss/selectApiDataDetailView.do?publicDataPk=3070842   
<br>  
  
- 데이터 파일3. gyeongnam_contour_simplified_30.gpkg   
  
: 등고선 데이터 
원본 데이터의 용량이 지나치게 크고(약 6기가) 종류가 많아서 필요한 경남 부분으로만 자르고   
기존 1미터 였던 데이터 30미터로 조정하였습니다.   
원본 데이터 실제 사용한 데이터로 바꾸는 부분 주석처리 하여 같이 올립니다.   

원본 데이터가 5기가가 넘어 사용한 원본 데이터의 일부만 첨부합니다   
원본 데이터의 일부: N3L_F0010000_B.dbf, N3L_F0010000_B.prj, N3L_F0010000_B.shx, N3L_F0010000_B.xml    
실제로는 BCDEFHG 파일을 합쳐 사용하였습니다 (B만 업로드)   

출처: https://www.vworld.kr/dtmk/dtmk_ntads_s002.do?dsId=30185   
제공 기관: 산림청    
<br> 
  
- 데이터 파일4. slope_gn.tif   

: 경사도 데이터   

원본데이터 중 gn (경남) 부분만 이용하였고   
그 중에 .tif 파일만 사용했습니다.   
가중치 중에 경사로 부분에서 사용하는   
위치별 경사에 대한 자료입니다.   

출처: https://www.bigdata-environment.kr/user/data_market/detail.do?id=c0a2e080-313c-11ea-adf5-336b13359c97#!   
제공 기관 : 한국 지질 자원 연구원  

### 실험 환경  

dbfread: 2.0.7   
geopandas: 1.0.1   
pandas: 2.2.3   
numpy: 2.2.5   
shapely: 2.1.0   
requests: 2.32.3   
matplotlib: 3.10.1   
seaborn: 0.13.2   
contextily: 1.6.2   
