# oss_winter_project

1.	모델 실행 
1.1	EfficientNet_ai_train.py
Train_path를 install한 train데이터폴더에서 사용자가 학습을 원하는 질병이미지가 존재하는 폴더로 설정
Ex) 백내장에 대하여 학습
Trian 폴더내부에 Catarct이미지폴더 path로 변경

**주의**
데이터 폴더 내부에는 일반 / 안구초음파 2개의 데이터셋에 대한 Train / val 데이터셋이 존재하고 train / val 데이터셋의 path를 일반이면 일반 , 안구초음파면 안구초음파 이미지를 사용하게 path설정을 해줘야함
학습은 일반으로 진행하고 , 검증은 안구초음파로 진행한다면 결과가 올바르게 출력되지 않음

Train path를 지정 후 efficientNet_ops_3.py파일로 이동 후 
이미지에서처럼 하나의 val path를 제외한 나머지 path들은 모두 주석처리
 
-> 위의 모든 경로의 학습을 진행은 모든 데이터셋을 이용할시에 가능
-> 작성자는 강아지의 백내장 데이터에 대한 학습을 실행하였기에 이미지에서처럼 val경로를 설정
모든 데이터셋의 경로설정까지 완료 후에 터미널창에서 아래 명령어를 입력
python efficientNet_ai_train.py
모델이 스스로 클래스별로 학습/검증 데이터를 구분해서 학습을 진행 

전체 Epoch는 작성자의 경우 100회로 설정하였고 , 사용자의 기호에 따라 자유롭게 Epoch 횟수는 조절가능 
100회 학습동안 일정 수의 학습 진행 후 모델이 model_saved 폴더에 학습된 모델과 
전체 train / val loss에 값의 csv파일 , Accuracy 그래프 이미지가 생성됨
