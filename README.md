# Corona Dashboard(Ongoing..)

본 프로젝트는 코로나 바이러스의 심각성을 인지하고,

시간에 따른 바이러스의 확산, 시/도 별 사망자 추이 등의 시각화를 다룰 예정입니다.

시각화 결과는 대시보드를 통해 구축되어집니다.


## Crawling

### 수집 사이트
| 그룹   | 지역 | 주소                                                           | Package    | Code |
|--------|------|----------------------------------------------------------------|------------|------|
| 수도권 | 서울 | https://www.seoul.go.kr/coronaV/coronaStatus.do                | `scrapy`   |      |
| 수도권 | 인천 | https://www.incheon.go.kr/health/HE020409                      | `scrapy`   |      |
| 수도권 | 경기 | https://www.gg.go.kr/bbs/board.do?bsIdx=722&menuId=2903#page=1 | `Selenium` |      |


### 실행
```
git clone https://github.com/pyy0715/Corona19_Dashboard.git
cd Corona19_Dashboard/corona_crawl/corona_crawl
conda env create -f environment.yml

# 서울
scrapy crawl seoul -o data/seoul.csv -t csv

# 인천
scrapy crawl incheon -o data/incheon.csv -t csv

# 경기
python gyeonggi.py
```

### 참고사항

> 일부 사이트의 경우 나이가 아닌 출생년도만 표시되기 때문에, 
> 10~20년도 사이의 출생자들은 판단하기 어려운 경우가 있었음.
> 이러한 경우, 99세 기준 1922년도를 정하고 미만의 출생자들은 밀레니엄 세대로 분류함.



## EDA
`plotly`
`Bokeh`

## Dashboard
`Streamlit`
