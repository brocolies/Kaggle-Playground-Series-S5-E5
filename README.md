# 🏆 Kaggle Playground Series - Season X Episode Y

> **문제 유형:** Regression
> **목표:** Predict calories consumtion 
> **평가 지표:** RMSLE  
> **데이터 크기:** train data 750k rows, test data 250k rows

---

## 📁 File Structure

| File                | 설명 |
|---------------------|------|
| `train.csv`         | 학습용 데이터 |
| `test.csv`          | 테스트 데이터 |
| `sample_submission.csv` | 제출 형식 예시 |
| `PredictCal2.ipynb`  | 전체 분석 노트북 |
| `submission.csv`    | 최종 제출 파일 |

---

## 📌 프로젝트 목표

- [ ] EDA를 통해 이상치 및 분포 확인
- [ ] 도메인에 맞는 Feature Engineering 설계
- [ ] 적절한 모델 선택 (XGBoost, LGBM 등)
- [ ] Evaluation Metric 기준 최적화
- [ ] 최종 제출 파일 생성 및 검증

---

## 🔎 주요 Feature Engineering

| Feature 이름 | 설명 |
|--------------|------|
| `BMI`        | 체중과 키로부터 계산된 BMI |
| `Intensity`  | Heart Rate + Body Temp 기반 운동 강도 |
| `EnergyProxy`| Duration × Intensity 기반 소모량 근사치 |

---

## 📊 모델 정보

| 항목          | 설정 |
|---------------|------|
| 사용 모델     | XGBoost |
| 파라미터 조정 | learning_rate=0.05, max_depth=6, n_estimators=1000 |
| 평가 지표     | RMSLE |
| 검증 방식     | train_test_split (80:20) |

---

## ✅ 결과 요약

| 단계 | 점수 |
|------|------|
| Local Validation RMSLE | 0.0629 |
| Kaggle Public Score     | 0.57409 |

---

## 🚀 향후 개선점

- [ ] Feature Selection 및 중요도 기반 제거
- [ ] Cross Validation으로 평가 안정화
- [ ] 모델 앙상블 실험 (Stacking / Voting)
- [ ] Feature scaling & outlier clipping 고도화

---

## 📌 참고 사항

- 코드 작성은 Jupyter 기반으로 진행
- 제출 기준은 `submission.csv` (id, target 형식)
- Kaggle 대회 링크: [https://www.kaggle.com/competitions/your-competition](https://www.kaggle.com/competitions/your-competition)
