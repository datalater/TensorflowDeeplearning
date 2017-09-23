  
ⓒ JMC 2017
  
**SOURCE**  
\- 텐서플로로 시작하는 딥러닝, 나카이 에츠지
  
---
  
## I. 반복숙달용 Summary Questions
  
  
### Q1-1. 데이터를 모델링하는 3단계
  
  
+ 1\) 주어진 데이터를 기반으로 미지의 데이터를 예측하는 '**모델 방정식**'을 생각한다.
+ 2\) 모델 방정식에 포함된 파라미터의 좋고 나쁨을 판단하는 '**오차 함수**'를 준비한다.
+ 3\) 오차 함수를 최소화하는 '**최적의 파라미터값**'을 결정한다.
  
### Q1-2. 모델의 뜻
  
  
+ 데이터를 설명하는 방정식
  
### Q1-3. 머신러닝에서 컴퓨터가 하는 역할 (=텐서플로의 주요 업무)
  
  
+ **파라미터 최적화** : 오차 함수를 최소화하는 계산을 정해진 알고리즘을 이용해 자동으로 계산하는 것이 머신러닝에서 컴퓨터가 하는 역할이며, 텐서플로의 주요 업무다.
  
### Q1-4 분류 문제에서 모델링하는 3단계
  
  
+ 1\-1) 두 class의 경계를 나타내는 '**직선 형태의 모델 방정식(linear classifier)**'을 생각한다.
+ 1\-2) linear classifier를 sigmoid 함수에 대입해서 두 '**class에 속할 확률값**'을 도출한다.
+ 2\) linear classifier에 포함된 파라미터의 좋고 나쁨을 판단하는 '**오차 함수**'를 준비한다.
+ 3\) 오차 함수를 최소화하는 '**최적의 파라미터값**'을 결정한다.
  
> **Note:** `linear classifier`란 분류 문제에서 사용하는 직선 형태의 모델을 뜻한다. || linear classifier 방정식 : <img src="https://latex.codecogs.com/gif.latex?f(x_1,%20x_2)%20=%20w_0%20+%20w_1x_1%20+%20w_2x_2%20=%200"/> || linear classifier로 계산된 score 값을 0부터 1까지의 값을 가지는 함수에 대입하면 `각 class에 속할 확률값`인 <img src="https://latex.codecogs.com/gif.latex?P(x_1,%20x_2)"/>를 구할 수 있다.
  
### Q1-5 신경망이 데이터 모델링 3단계에서 가지는 의미
  
  
+ 데이터 모델링 1단계에서 데이터를 설명하는 모델은 사람이 생각해내야 한다.
+ 데이터의 차원이 아주 높다면 사람의 뇌로는 상상조차 할 수 없다.
+ 그런데 '**신경망**'은 '**하나의 단순한 수식이 아니라 여러 개의 수식을 조합한 함수**'를 사용해서 다양한 데이터에 대응할 수 있는 모델이라는 데에 의미가 있다.
  
---
  
## II. Summary Questions에 아직 등록되지 않은 Note
  
  
### 01 신경망이 데이터 모델링 3단계에서 가지는 의미
  
  
신경망은 데이터 모델링의 1단계에서 의미가 있다. 데이터를 설명하는 모델을 떠올리는 것은 사람이 해내야 하는 몫이다. 그런데 데이터의 차원이 3차원을 넘어가면 사람의 머릿속으로는 상상할 수조차 없다. 지금까지 다양한 데이터에 대응할 수 있는 모델 방정식을 생각해내려는 노력이 이어져 왔는데, 그 중 하나가 신경망이다. '**신경망**'은 '**하나의 단순한 수식이 아니라 여러 개의 수식을 조합한 함수를 사용**'해서 다양한 데이터에 대응할 수 있는 모델이라는 데에 의미가 있다.
  
### 01 신경망의 노드를 늘리는 방법
  
  
+ 복잡하게 뒤섞인 데이터에 대응하려면 복잡한 신경망을 이용해야 한다.
+ 이때 노드를 증가시키는 방법은 2가지가 있다.
    + 1\) 계층의 수를 늘리는 방법
    + 2\) 하나의 계층에 포함된 노드의 수를 늘리는 것
  
### 01 딥러닝
  
  
딥러닝은 다층 신경망을 이용한 머신러닝에 지나지 않는다.
다만, 단순히 계층을 증가시켜 복잡하게 만든 것이 아니라, 각 노드의 역할을 생각하면서 특정 의도를 갖고 구성한 신경망을 뜻한다.
  
### 01 딥러닝 모델을 생각할 때 필요한 시행착오
  
  
+ 딥러닝 모델을 구성할 때는 주어진 데이터가 어떻게 처리될지를 생각하면서 최적의 네트워크를 구성해야 한다.
  
### 01 CNN을 구성하는 각 노드의 역할
  
  
+ convolution layer : 이미지에 나타난 물체의 특징을 정확하게 포착한다.
+ pooling layer : 이미지의 세밀한 부분을 지워서 물체의 본질적인 특징만을 추출한다.
  
### 01 RNN을 구성하는 중간 계층 노드의 역할
  
  
+ 자연스러운 문장을 판단하는 RNN의 경우 '**과거의 입력값 정보가 중간 계층에 축적**'되어 긴 단어열을 바탕으로 판정한다.
  
### 01 RNN에 필요한 테크닉
  
  
+ 이전에 입력한 단어 정보는 중간 계층에서 서서히 사라지게 되므로 노드 간 연결 방식을 좀 더 연구해서 '**과거의 정보를 가능한 한 오래 축적하는 등의 테크닉**'이 이용된다.
  
  
### 01 텐서플로를 이용한 파라미터 최적화
  
  
#### 1) 오차 함수는 파라미터에 대한 함수이다
  
  
<img src="https://latex.codecogs.com/gif.latex?(1)%20&#x5C;%20L%20=%20&#x5C;frac{1}{2}&#x5C;Sigma(y_i%20-%20t_i)^{2}"/>
  
오차 함수에는 모델의 방정식이 포함된다.
  
<img src="https://latex.codecogs.com/gif.latex?(2)%20&#x5C;%20y_i%20=%20w_0%20+%20w_1x_1%20+%20w_2x_2%20+%20w_3x_3%20+%20w_4x_4%20=%20&#x5C;Sigma%20w_ix_i"/>
  
모델의 방정식에는 파라미터가 포함된다.
  
<img src="https://latex.codecogs.com/gif.latex?(3)%20&#x5C;%20L(w_0,%20w_1,%20w_2,%20w_3,%20w_4)%20=%20&#x5C;frac{1}{2}&#x5C;Sigma(&#x5C;Sigma%20w_ix_i%20-%20t_i)^{2}"/>
  
따라서 파라미터 값이 변경되면 오차 함수의 값도 변화한다.
결국 오차 함수는 파라미터에 대한 함수라고 볼 수 있다.
  
#### 2) 오차 함수를 각 parameter로 편미분한 값을 0으로 두는 연립방정식을 푼다
  
  
이제 식 (3)의 값을 최소로 하는 <img src="https://latex.codecogs.com/gif.latex?w_0,%20w_1,%20w_2,%20w_3,%20w_4"/>의 값을 결정한다.
구체적으로는 식 (3)을 <img src="https://latex.codecogs.com/gif.latex?w_0,%20w_1,%20w_2,%20w_3,%20w_4"/> 각각으로 편미분한 값을 0으로 하는 다음과 같은 연립방정식을 푸는 것이다.
  
<img src="https://latex.codecogs.com/gif.latex?(4)%20&#x5C;%20&#x5C;frac{&#x5C;partial%20L}{&#x5C;partial%20w_i}(w_0,%20w_1,%20w_2,%20w_3,%20w_4)%20=%200"/>
  
편미분하는 작업은 수학을 좋아하는 사람에게 숙제로 남겨 두고 여기서는 식 (4)의 조건으로 L이 최소가 되는 이유를 설명하겠다.
  
#### 3) "오차함수의 편미분 = 0"으로 두면 오차 함수가 최소가 되는 이유
  
  
<img src="https://latex.codecogs.com/gif.latex?L(w_0,%20w_1,%20w_2,%20w_3,%20w_4)"/>와 같은 다변수 함수의 경우 편미분하면 어떻게 될까?
간단하게 설명하기 위해 2변수 함수의 편미분을 생각해보자.
  
<img src="https://latex.codecogs.com/gif.latex?(5)%20&#x5C;%20h(x_1,%20x_2)%20=%20&#x5C;frac{1}{4}(x_1^{2}%20+%20x_2^{2})"/>
  
<img src="https://latex.codecogs.com/gif.latex?(6)%20&#x5C;%20&#x5C;frac{&#x5C;partial%20h}{&#x5C;partial%20x_1}%20=%20&#x5C;frac{1}{2}x_1,%20&#x5C;%20&#x5C;frac{&#x5C;partial%20h}{&#x5C;partial%20x_2}%20=%20&#x5C;frac{1}{2}x_2"/>
  
<img src="https://latex.codecogs.com/gif.latex?(7)%20&#x5C;%20&#x5C;triangledown%20h(x_1,%20x_2)%20=%20&#x5C;begin{pmatrix}&#x5C;frac{1}{2}x_1%20&#x5C;&#x5C;&#x5C;frac{1}{2}x_2&#x5C;end{pmatrix}%20=%20&#x5C;frac{1}{2}%20&#x5C;begin{pmatrix}x_1%20&#x5C;&#x5C;x_2&#x5C;end{pmatrix}"/>
  
편미분한 벡터를 식 (7)처럼 triangledown 기호로 나타내며, 함수 <img src="https://latex.codecogs.com/gif.latex?h(x_1,%20x_2)"/>이 '**기울기 벡터(gradient vector)**'라고 한다.
  
기울기 벡터에는 도형에서의 의미가 있다.
  
`#inProgress: p.19 [그림1-14] 2변수 함수의 기울기 벡터 `
  
---
  