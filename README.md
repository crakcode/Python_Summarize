PageRank
그래프 정점에 일정한 값의 가중치를 부여한다(A,B,C,D)의 4개의 정점이 있는 경우 0.25씩 균등하게 분배한다.
이후 그래프의 상태를 확인한다. 그래프의 연결 상태에서  A는 B,D 연결 되어있고 B는 A,D에 연결되었다.
D는 A,B,C 모두 연결되어있고 나머지 C는 D하고만 연결되어 있다. 이러한 상태를 파악한뒤 자신이 가진 가중치를
분배한다. A는 B,D 와 연결이 되어있기 때문에 1.25씩 분배한다. 그리고 각각 정점에 받은 가중치에 0.85를 곱하고 
랜덤서퍼 모델: 15%를 가진다는 가정하에 0.15* 0.25를 곱해준다.

1. 정점에 각각 받은 가중치 * 0.85
2. 랜덤서퍼모델 가중치* 0.25
1+2를하여서 가중치를 업데이트 한다. 업데이트 하는 경우 연결 상태에서 가장 연결이 많이 된 순서대로 
값이 형성 되게 되는데 D가 가장 0.463으로 가장 높고 A,B 그리고 C 순으로 높다 
즉 연결이 가장 많이 된경우가 가중치가 가장 높음을 확인할수있다.

TextRank
Text Rank는 PageRank를 활용한 알고리즘 방식이다 .

텍스트 단위로서 추출
각각의 단어를 정점으로 잡고, 한 문장 내에서 같이 등장하는 동시 출현 빈도를 가지고 간선을 구축할 수 있다. 
이 경우 텍스트 랭크 값은 각 단어의 중요도를 표현하게 되므로, 중요도가 높은 단어를 추출하게 되면 주요 키워드 추출(Keyword Extraction)이다.



텍스트 단위로써의 문장
단위를 더 크게 잡아서 각각의 문장을 정점으로 잡고, 문장 간의 유사도를 가지고 간선을 구축할 수도 있다. 
이 경우 텍스트 랭크 값은 각 문장의 중요도를 표현하게 됩니다. 중요도가 높은 문장을 추려내서 새로운 글을 
만들게 되며 이는 텍스트 요약(Text Summarization)이다.


한국어 텍스트에 적용해보기
TF는 단어 빈도, TR은 TextRank값입니다. 
표에서 볼수 있듯이 자주 등장하는 단어일수록 TR 값 역시 높지만 둘이 완전 일치하지는 않는다는 것을 알 수 있습니다. 
근데 키워드로 뽑아낼 어구가 토큰화 과정에서 단어별로 쪼개져 버렸습니다. 
'외계 행성'이 '외계'와 '행성'으로 나눠져 나오기보다는 하나로 묶여 나오는게 좋겠죠. 
그렇기 때문에 연속해서 같이 등장하는 단어는 합쳐줄 필요가 있습니

적절한 지점에서 끊어주는게 필요합니다. 정점 안에는 TextRank값, 간선에는 PMI값을 넣었다
이를 이용해 좋은 키워드 후보를 계산한다. 이러한 방식을 문장에 적용하여 문장을 요약할수있다.

 

출처:https://bab2min.tistory.com/552

 
