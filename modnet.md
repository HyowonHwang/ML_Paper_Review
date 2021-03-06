# ModNet
 - Real Time Background Removal
 - Trimap free matting 이라고 함. 

# Framwork Pipeline
 - 기본적으로 많은 테크닉이 사용된다.
 - <img width="1161" alt="스크린샷 2020-12-28 오후 8 11 23" src="https://user-images.githubusercontent.com/7637498/103210423-f3b30200-4948-11eb-88f6-842cec1bed30.png">

# ModNet
 - 기본적으로 MultiBranch 로 구성
 - <img width="1191" alt="스크린샷 2020-12-29 오전 10 11 19" src="https://user-images.githubusercontent.com/7637498/103252257-5c3cc600-49bf-11eb-8748-eb9cca2afb38.png">
  - 샘플코드나 Backbone 은 MobileNetV2
  - Branch 간의 Concat 이 다양하게 이루어 진다(기존에 보던 것과는 조금은 다름) __--__

# 현실 데이터를 적용 하기 위한 노력
 - Sub-Objectives Consistency (SOC)
 - One-Frame Delay (OFD)

# 벤치마크 툴
 - PPM-100

# Performance
 - General Performnace 
    - 512 × 512 input size, 63fps on 1080ti

# 용어
 - Trimap
   - foreground, background, unknown 이다.
   - 트라이의 의미는 'foreground와 background는 이미 확실하게 구분되었고 unknown 영역만 잘 구분하면 된니까 한번 잘 나눠봐라' 라는 의미거나 
영역을 3개로 나눴다는 의미인것 같다.

 - Matte 는 오브젝트만의 알파채널이다.
 
 # 궁금한점
 - 다른 Segmentation 모델을 봤을 경우 한 브랜치의 마지막 output 을 다른 브랜치와 Concat 했던 것이 대부분이였던 것 같은데 여기서는 굉장히 concat 흐름이 다양 한거 같음.
   - 이게 효과가 많이 주는 것인지?
   
 

# Reference
- https://www.catalyzex.com/paper/arxiv:2011.11961?fbclid=IwAR0MJ0RlpabmxeS4KAORk7m78olQNWIJBmMJa36tHnDSrLw4WO2BEwAGZmU
