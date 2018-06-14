# Brainsignal_Classification

1. 프로젝트 개요
   - 프로젝트 명: Keras 환경에서의 LSTM을 활용한 전두엽 혈류 활성화 변화도 Multi-classification
   - 연구 목적: 뇌 혈류량 측정장치인 fNIRS에서 측정한 데이터를 기반으로 3가지의 task에 대한 classification을 하여 BCI에 활용한다.

2. 사용한 데이터셋
   - time-series 데이터 셋: 7035 * 17 time-series 데이터, 8명의 데이터 셋
   - 라벨 정보 : 3 class 분류라벨

3. 사용한 모델: LSTM

4. 딥 러닝 라이브러리: keras

5. 

6. 2번째 코드 셀의
df = pd.read_csv('./data/sub1_total.txt', sep=',', 
                 parse_dates={'dt' : ['Time']}, infer_datetime_format=True, 
                 low_memory=False, na_values=['nan','?'], index_col='dt')
df1 = pd.read_csv('./data/sub2_total.txt', sep=',', 
                  parse_dates={'dt' : ['Time']}, infer_datetime_format=True, 
                 low_memory=False, na_values=['nan','?'], index_col='dt')

...

df7 = pd.read_csv('./data/sub8_total.txt', sep=',', 
                 parse_dates={'dt' : ['Time']}, infer_datetime_format=True, 
                 low_memory=False, na_values=['nan','?'], index_col='dt')

위 코드의 './data/sub피험자번호_total.txt' 부분을 data path에 따라 수정하시면 볼 수 있습니다.
