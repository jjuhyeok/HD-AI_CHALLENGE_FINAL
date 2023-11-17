# HD-AI_CHALLENGE_FINAL

## 🏆 Result
- **Leader Board Score(1st)**

<br>

<br>

<img width="100%" src="https://github.com/jjuhyeok/HD-AI_CHALLENGE_FINAL/assets/49608953/a1e39165-c040-490e-88d5-e8be7042a4ce"/>  
<br>

<br>

주최 : HD한국조선해양 AI Center  
  
주관 : DACON   
  
규모 : 총 1320여명 참가 중 최종 상위 11팀 본선 진출 후 진행된 본선 대회

<br>
==========================================================
  
  

  

✏️
**대회 느낀점**  
이번 본선 대회는 약 3일간의 짧은 기간으로 진행되었는데  
먼저 드는 생각은 정말 후회 없이 열심히 했다고 생각합니다.  
모델도 3일이라는 시간동안 총 400번 제출이 가능했는데  
혼자 380번 이상을 제출했었습니다.  
정말 열심히 했었고 마지막날에는 코딩하다가 코피도 여러번 났었습니다..  
이번 대회는 대회의 배경에 따른 가설 설정을 초점으로 진행했습니다.  
따라서 설정했던 가설로 모델링을 진행했는데,   
그 가설이 맞았기 때문에 아마 리더보드(모델 정확도) 랭킹도 1등이지 않았을까 라고 생각하며  
본선 발표 평가 때 심사위원분들께 잘 설득이 되지 않았나 라고 생각합니다.  

<br>
<br>



<br>

<br>
===========================================================================


## Data Info
<br>
  
* train.csv  
각 운전자의 작업 중량 정보가 이름으로 주어진 csv 16개(0, 100, 200, 300... 902 kg)
 -
 - 비식별화된 센서 및 시그널 데이터

* test.csv  
약 4000여 운전자의 센서 및 시그널 데이터


* sample_submission.csv  
각 운전자에 대한 작업 중량 예측

---

## Process

**1. EDA**   
  * 나라별, 항구별, 배의 타입별 등등의 특성 확인  
  * 각 배의 카테고리컬한 피처들의 조합의 통계값들 확인  
  * 기상정보에 대한 Target값 로직 파악  
  
**2. Feature Engineering**   
  * 시간 feature들은 inherently cyclical 하다는 특징을 활용하기 위해 sin/cos 변환  
  * 특정 피처들의 target 값의 평균으로 파생 변수 생성  
  * 클러스터링  


**3. Modeling**

  * Optuna를 활용하여 하이퍼파라미터 튜닝  

**3. Validation**
  * 일반적인 K-fold  
  * Year 따른 Stratify K-fold  
  * ARI_CO(나라별)에 따른 Stratify K-fold  
  * ARI_PO(항구별)에 따른 Stratify K-fold (public과 제일 Score 유사 but ARI_PO 샘플이 적은 항구들이 존재)  


  
