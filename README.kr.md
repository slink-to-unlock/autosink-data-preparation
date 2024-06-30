# Data Preparation for Autosink Project

[🇬🇧](README.md) | [🇰🇷](README.kr.md) | [🇨🇳](README.zh-CN.md)

사전적으로 data preparation 컴포넌트는 원래 raw data 를 가져오는 역할을 맡는다. 하지만 우리의 `autosink` 프로젝트의 시스템에서는 feature store 이라는 것이 존재하기 때문에, data preparaiton 이 raw data 를 가져오는 역할을 하지는 않는다. raw data 를 가져오는 일이 아니라 data preparation 에서 해야 하는 일을 image augmentation 같은 데이터 전처리라고 바라보았다. 이때, 데이터 전처리 결과물은 사실 feature store 에 저장이 되어 있을 것이다. 이 패키지는 전처리가 완료된 결과물을 먼저 feature store 에서 탐색하고, 이것이 없다면 data preprocessing 을 수행하고 해당 입력을 다운스트림 컴포넌트에 전달하는 역할을 수행한다.

## 기능

- [ ] 데이터 전처리를 수행한 데이터셋 반환
- [ ] 데이터 전처리 수행 전 feature store 우선 탐색 후 반환
