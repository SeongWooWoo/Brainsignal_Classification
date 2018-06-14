# Brainsignal_Classification

1. 프로젝트 개요
   - 프로젝트 명: Keras 환경에서의 LSTM을 활용한 전두엽 혈류 활성화 변화도 Multi-classification
   - 연구 목적: 뇌 혈류량 측정장치인 fNIRS에서 측정한 데이터를 기반으로 3가지의 task에 대한 classification을 하여 BCI에 활용한다.

2. 사용한 데이터셋
   - time-series 데이터 셋: 7035 * 17 time-series 데이터, 8명의 데이터 셋
   - 라벨 정보 : 3 class 분류라벨

3. 사용한 모델: LSTM

4. 딥 러닝 라이브러리: keras

5. 실험 내용 및 결과

기능적 근적외선분광기(fNIRS)를 이용하여 특정 작업 수행 시 측정한 뇌신호를 machine learning을 사용하여 작업별로 분류하는 것을 목적으로 함.
Task는 mental arithmetic, mental counting, puzzle solving 3가지 이며 각 세션은 5번의 시행으로 구성.
실험에 사용된 장비는 ISS Imagent fNIRS 장비이며 690nm, 830nm 파장을 사용하며 sampling rate는 15.625Hz 임.
측정 영역은 설정한 task에 반응하는 영역인 전두엽피질이며 총 채널수는 16개 임.
얻어진 데이터는 MBLL(Modified-Beer Lambert Law)에 의해 대뇌 피질의 HbO, HbR 농도로 계산 후 band-pass filtering(0.01~0.1Hz).
각 trial(task+rest:30sec)단위로 데이터 분할 (15.625*30=468개의 데이터 포인트)

6.  2번째 셀의

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

위 코드의 './data/sub피험자번호(1~8)_total.txt' 부분을 data path에 따라 수정하시면 볼 수 있습니다.
