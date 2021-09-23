# Project_Kermit
## Project Kermit의 목적은 이렇습니다.
사용자와 챗봇이 원활하게 대화할 수 있는 어플리케이션을 만드는 것,</br>
이를 개발하기 위해 여러 챗봇에서 쓰이는 자연어 처리 모델에 대해서 이해하고 설계할 수 있도록 공부하고 활용하는 것

## Kermit에 대한 설명
개굴. Kermit은 "한글을 배운 개구리" 라는 컨셉을 가진, 대화형 인공지능 챗봇입니다.</br>
개굴. 이 프로젝트는 단대소프트고 20412 박은혁, 20413 신지원 학생이 제작한 프로젝트입니다. </br>
개굴. 원래 Bert 모델을 사용하여 학습하려 했으며 그래서 프로젝트명도 Kermit이 됐지만, Text Generation에는 Bert가 적합하지 않아 Ko-GPT2 모델을 사용하여 학습했습니다.</br>
개굴. 한글을 갓 배운 개구리답게 능숙하게 대화를 하지 못하고 일부 어색한 문장을 만들어내기도 합니다. 너그럽게 이해해주세요.</br>

## Kermit 프로그램 흐름도
![image](https://user-images.githubusercontent.com/35924139/134572105-0643c4f8-3303-4990-ae47-90ec22f9ec0a.png)

## Kermit GPT2
**Kermit_GPT2_TextGeneration.ipynb** : 모델을 불러오고 챗봇 대화 데이터셋을 임베딩, 토큰화하여 학습합니다.
**Kermit_GPT2_ChatbotTesting.ipynb** : 학습된 모델 pth 파일을 불러와 Text Generation을 수행합니다.
```class DialogKoGPT2(nn.Module):
  def __init__(self):
    super(DialogKoGPT2, self).__init__()
    self.kogpt2 = get_kogpt2_model()

  def generate(self,
               input_ids,
               do_sample=True,
               max_length= 60,
               top_p=0.92,
               top_k=50,
               temperature= 0.6,
               no_repeat_ngram_size =None,
               num_return_sequences=3,
               early_stopping=False,
               ):
    ...생략
```
DialogKoGPT2 클래스는 KoGPT2 모델을 불러와서 generate를 수행합니다. (Huggingface의 how-to-generate-text 문서 참조)

## Kermit 포스터
![kermit](https://user-images.githubusercontent.com/35924139/134570770-a337d942-c418-406e-991f-304b2af5a42a.png)
