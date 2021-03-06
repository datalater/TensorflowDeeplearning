
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

### Q1-4. 분류 문제에서 모델링하는 3단계


+ 1\-1) 두 class의 경계를 나타내는 '**직선 형태의 모델 방정식(linear classifier)**'을 생각한다.
+ 1\-2) linear classifier를 sigmoid 함수에 대입해서 두 '**class에 속할 확률값**'을 도출한다.
+ 2\) linear classifier에 포함된 파라미터의 좋고 나쁨을 판단하는 '**오차 함수**'를 준비한다.
+ 3\) 오차 함수를 최소화하는 '**최적의 파라미터값**'을 결정한다.

> **Note:** `linear classifier`란 분류 문제에서 사용하는 직선 형태의 모델을 뜻한다. || linear classifier 방정식 : <img src="https://latex.codecogs.com/gif.latex?f(x_1,%20x_2)%20=%20w_0%20+%20w_1x_1%20+%20w_2x_2%20=%200"/> || linear classifier로 계산된 score 값을 0부터 1까지의 값을 가지는 함수에 대입하면 `각 class에 속할 확률값`인 <img src="https://latex.codecogs.com/gif.latex?P(x_1,%20x_2)"/>를 구할 수 있다.

### Q1-5. 신경망이 데이터 모델링 3단계에서 가지는 의미


+ 데이터 모델링 1단계에서 데이터를 설명하는 모델은 사람이 생각해내야 한다.
+ 데이터의 차원이 아주 높다면 사람의 뇌로는 상상조차 할 수 없다.
+ 그런데 '**신경망**'은 '**하나의 단순한 수식이 아니라 여러 개의 수식을 조합한 함수**'를 사용해서 다양한 데이터에 대응할 수 있는 모델이라는 데에 의미가 있다.

### Q1-6. 파라미터를 최적화하는 방법


먼저 오차 함수는 파라미터에 대한 함수라는 것을 알아야 한다.
파라미터가 포함된 모델의 방정식이 오차 함수에 들어가 있다.
즉, **파라미터 값이 변경되면 오차 함수의 값도 변화하므로, 오차 함수는 파라미터에 대한 함수라고 볼 수 있다**.

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(1)%20&#x5C;%20L%20=%20&#x5C;frac{1}{2}&#x5C;Sigma(y_i%20-%20t_i)^{2}"/>

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2)%20&#x5C;%20y_i%20=%20w_0%20+%20w_1x_1%20+%20w_2x_2%20+%20w_3x_3%20+%20w_4x_4%20=%20&#x5C;Sigma%20w_ix_i"/>

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(3)%20&#x5C;%20L(w_0,%20w_1,%20w_2,%20w_3,%20w_4)%20=%20&#x5C;frac{1}{2}&#x5C;Sigma(&#x5C;Sigma%20w_ix_i%20-%20t_i)^{2}"/>

**오차 함수를 다변수 공간에 표현했을 때 함수값이 최소로 되는 최저점을 찾아야 한다**.
이 최저점은 '**기울기 벡터가 0이 되는 곳**'을 뜻한다.
기울기 벡터는 오차 함수를 각 parameter별로 편미분하면 구할 수 있다.
따라서 오차 함수를 편미분해서 기울기 벡터를 구하고 기울기 벡터가 0이 되는 곳을 찾으면, 오차 함수의 최소값을 구할 수 있게 된다.

**기울기 벡터의 크기가 0이 되는 곳까지 현재 위치의 기울기 벡터와 반대 방향으로 반복해서 내려간다**.

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(8)%20&#x5C;%20W^{new}%20=%20W%20-%20&#x5C;alpha%20&#x5C;triangledown%20L(W)"/>

    + <img src="https://latex.codecogs.com/gif.latex?W"/> : <img src="https://latex.codecogs.com/gif.latex?(w_0,%20w_1,%20w_2,%20w_3,%20w_4)"/>의 현재 위치(=좌표)
    + <img src="https://latex.codecogs.com/gif.latex?-%20&#x5C;triangledown%20L(W)"/> : 현재 위치 <img src="https://latex.codecogs.com/gif.latex?W"/>에서의 기울기 벡터와 반대방향으로 간다
    + <img src="https://latex.codecogs.com/gif.latex?-%20&#x5C;alpha%20&#x5C;triangledown%20L(W)"/> : 한 번 반대 방향으로 갈 때 <img src="https://latex.codecogs.com/gif.latex?&#x5C;alpha"/>만큼 이동한다
    + <img src="https://latex.codecogs.com/gif.latex?W^{new}"/> : 현재 위치에서 현재 위치에서의 기울기 벡터만큼 반대 방향으로 이동한 곳이 새로운 위치이다 (= 파라미터 갱신)

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(9)%20&#x5C;%20&#x5C;triangledown%20L(W)%20=%20&#x5C;begin{pmatrix}&#x5C;frac{&#x5C;partial%20L}{&#x5C;partial%20w_0}(W)%20&#x5C;&#x5C;&#x5C;vdots%20&#x5C;&#x5C;&#x5C;frac{&#x5C;partial%20L}{&#x5C;partial%20w_4}(W)&#x5C;end{pmatrix}"/>

이때 식 (8)에서 파라미터를 갱신할 때마다 그 점에서의 기울기 벡터 값을 식 (9)로 다시 계산한다는 점에 주의한다.
이렇게 '**현재 파라미터의 값에 대해 기울기 벡터를 계산하고, 그 반대 방향으로 파라미터를 수정하는 알고리즘**'을 '**경사 하강법(gradient descent**)'이라고 한다.
현실의 문제에서는 충분히 원점에 가까워졌을 때 계산을 중단하고, 그 시점의 값을 근사적인 최적해로 채택한다.
파라미터를 갱신하는 계산은 당연히 컴퓨터를 이용해 자동화하며, 이 부분이 머신러닝이나 딥러닝에서 텐서플로의 역할에 해당한다.
**training set의 양이 많은 경우 한 번에 모든 데이터를 이용해서 파라미터를 최적화하는 것이 아니라, 단계적으로 데이터를 투입해가면서 파라미터를 최적화해 가는 식의 테크닉도 필요하다**.

그런데 **오차 함수의 그래프가 여러 곳에 local minima가 있다면** 기울기 벡터가 0이 되는 곳이 여러 군데 존재하게 된다.
즉, 경사 하강법으로 global minimum에 도달하지 못할 수도 있다.
이와 같은 문제에 대응하기 위해 **확률적 경사 하강법(SGD)이나 미니 배치(mini-batch) 같은 테크닉을 사용한다**.

> **Note**: 2.3.4 미니배치와 확률적 경사 하강법

---

## II. Summary Questions에 아직 등록되지 않은 Note


### 02 확률을 이용해서 모델을 만들면 생기는 이점


+ 확률을 이용해서 모델을 만들면, 오차 함수로 자연스럽게 최우추정법(MLE)을 사용할 수 있다.

### 02 로지스틱 회귀를 이용한 이항 분류기


#### 데이터 모델링 1단계 : 모델 방정식 세우기 (1)


두 가지 검사 <img src="https://latex.codecogs.com/gif.latex?x_1,%20x_2"/>를 토대로 바이러스 감염, 비감염 판정을 내리는 training data가 있다.
training data를 시각화하면 <img src="https://latex.codecogs.com/gif.latex?x_1,%20x_2"/>축을 가진 그래프에서 감염(o), 비감염(x)을 나타내는 데이터 포인트가 찍힌다.
우리의 목적은 데이터의 분류이므로 데이터 포인트 (o)와 (x)를 분리하는 직선을 그을 수 있다.
두 데이터의 경계를 나타내는 이 직선을 linear classifier라고 한다.
linear classifier는 분류 문제에서 데이터의 경계를 나눠서, 어떤 데이터가 어느 클래스에 속하는지 설명해주므로 '모델'이 된다.
모델은 다음과 같이 수식으로 나타낼 수 있다.

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2.1)%20&#x5C;%20f(x_1,%20x_2)%20=%20w_0%20+%20w_1x_1%20+%20w_2x_2"/>

#### 데이터 모델링 1단계 : 모델 방정식 세우기 (2)


우리의 목표는 새로운 검사 결과 <img src="https://latex.codecogs.com/gif.latex?(x_1,%20x_2)"/>가 나왔을 때 이 환자가 실제로 감염되었는지 판정하는 것이다.
<img src="https://latex.codecogs.com/gif.latex?x_1,%20x_2"/>축을 가진 그래프에 새로운 환자의 데이터가 찍혔다고 해보자.
이를 단순하게 감염(o) 또는 비감염(x)으로 분류하는 것이 아니라 이 환자가 바이러스에 감염되었을 확률을 구하고자 한다.
<img src="https://latex.codecogs.com/gif.latex?f(x_1,x_2)"/>의 값은 <img src="https://latex.codecogs.com/gif.latex?&#x5C;pm%20&#x5C;infty"/>를 향해 변화하므로 확률 값으로 적절하지 않다.
<img src="https://latex.codecogs.com/gif.latex?f(x_1,x_2)"/>의 범위를 확률의 범위 0~1 사이로 맞추기 위해 시그모이드 함수에 대입한다.

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2.2)%20&#x5C;%20-&#x5C;infty%20&lt;%20f(x_1,x_2)%20&lt;%20+&#x5C;infty"/>

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2.3)%20&#x5C;%200%20&lt;%20&#x5C;sigma%20(x)%20=%20&#x5C;frac{1}{1%20+%20e^{-x}}%20&lt;%201"/>

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2.4)%20&#x5C;%200%20&lt;%20&#x5C;sigma%20(f(x_1,%20x_2))%20&lt;%201"/>

결국 우리의 모델은 다음과 같이 표현된다.

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2.5)%20&#x5C;%20P(x_1,%20x_2)%20=%20&#x5C;sigma%20(f(x_1,%20x_2))%20=%20&#x5C;frac{1}{1%20+%20e^{-(w_0%20+%20w_1x_1%20+%20w_2x_2)}}"/>

#### 데이터 모델링 2단계 : 오차 함수 준비 (1)


"확률을 이용해서 예측 모델을 만들면, 파라미터의 좋고 나쁨을 평가하는 오차 함수로 자연스럽게 최우추정법(MLE)를 사용할 수 있다는 이점이 있다."
식 (2.5)에서 만든 모델에 포함된 파라미터의 좋고 나쁨을 어떻게 판단할 수 있을까?
주어진 training data를 잘 맞히는지 알아보면 된다.
엄밀히 말하자면, 수많은 parameter 조합 중에서 training data를 예측할 확률이 가장 높은 parameter를 선택하면 된다.
이와 같이 주어진 데이터를 바르게 예측할 확률을 최대화하는 것을 최우추정법(Maximum Likelihood Estimation)이라고 한다.

> **Note**: 모델 방정식에 포함된 parameter가 가질 수 있는 값은 무한 개이다. 즉, 가능한 모델의 개수 또한 무한 개이다. 최우추정법에서는 모델 여러 개 중에서 주어진 데이터를 예측할 확률이 가장 높은 모델을 선택하는 알고리즘이다.

트레이닝 데이터 N개를 표현하면 식 (2.6)과 같다.
<img src="https://latex.codecogs.com/gif.latex?n"/>번째 데이터 <img src="https://latex.codecogs.com/gif.latex?(x_{1_{n}},%20x_{2_{n}})"/>의 바이러스 감염 여부를 <img src="https://latex.codecogs.com/gif.latex?t_n%20&#x5C;in%20&#x5C;{0,%201&#x5C;}"/>이라고 하자. <img src="https://latex.codecogs.com/gif.latex?n"/>번째 데이터를 바르게 예측할 확률을 <img src="https://latex.codecogs.com/gif.latex?P_n"/>이라고 할 때 식 (2.7)과 식 (2.8)이 성립한다.

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2.6)%20&#x5C;%20(x_{1_{1}},%20x_{2_{1}}),%20(x_{1_{2}},%20x_{2_{2}}),%20&#x5C;cdot%20&#x5C;cdot%20&#x5C;cdot,%20(x_{1_{N}},%20x_{2_{N}})"/>

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2.7)%20&#x5C;%20[%20&#x5C;begin{array}{ll}%20t_n=1%20:%20P_n%20=%20P(x_{1_{n}},%20x_{2_{n}})%20&#x5C;&#x5C;t_n=0%20:%20P_n%20=%201%20-%20P(x_{1_{n}},%20x_{2_{n}})&#x5C;end{array}"/>

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2.8)%20&#x5C;%20P_n%20=%20&#x5C;{%20P(x_{1_{n}},%20x_{2_{n}})%20&#x5C;}^{t_n}%20&#x5C;{%201%20-%20P(x_{1_{n}},%20x_{2_{n}})%20&#x5C;}^{1-t_n}"/>

<img src="https://latex.codecogs.com/gif.latex?n"/>번째 데이터가 아니라 <img src="https://latex.codecogs.com/gif.latex?N"/>개 데이터 모두 정답일 확률 <img src="https://latex.codecogs.com/gif.latex?P"/>를 계산해보자.
이는 각 데이터를 바르게 예측학 확률의 곱셈으로 계산할 수 있다.
식 (2.10)이 우리가 만든 모델 (2.5)의 우도 함수이자 오차 함수이다.

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2.9)%20&#x5C;%20P%20=%20P_1%20&#x5C;times%20P_2%20&#x5C;times%20&#x5C;cdots%20&#x5C;times%20P_N%20=%20&#x5C;Pi_{n=1}^{N}P_n"/>
+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2.10)%20&#x5C;%20P%20=%20&#x5C;Pi_{n=1}^{N}&#x5C;{%20P(x_{1_{n}},%20x_{2_{n}})%20&#x5C;}^{t_n}%20&#x5C;{%201%20-%20P(x_{1_{n}},%20x_{2_{n}})%20&#x5C;}^{1-t_n}"/>

#### 데이터 모델링 2단계 : 오차 함수 준비 (2)


텐서플로로 계산할 경우 식 (2.10)과 같이 곱셈을 대량으로 포함하는 수식은 계산 효율이 좋지 않다.
덧셈으로 대체하려면 오차 함수에 <img src="https://latex.codecogs.com/gif.latex?&#x5C;log"/>를 취하면 되는데, <img src="https://latex.codecogs.com/gif.latex?P"/>는 클수록 좋지만 오차 함수의 값은 작으면 좋으므로 <img src="https://latex.codecogs.com/gif.latex?-&#x5C;log"/>를 취해준다.

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2.11)%20&#x5C;%20L%20=%20-%20&#x5C;log%20P"/>
+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2.12)%20&#x5C;%20L%20=%20-%20&#x5C;log%20&#x5C;Pi_{n=1}^{N}&#x5C;{%20P(x_{1_{n}},%20x_{2_{n}})%20&#x5C;}^{t_n}%20&#x5C;{%201%20-%20P(x_{1_{n}},%20x_{2_{n}})%20&#x5C;}^{1-t_n}"/>
+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2.13)%20&#x5C;%20L%20=%20-%20&#x5C;Sigma_{n=1}^{N}%20[t_n%20&#x5C;log%20P(x_{1_{n}},%20x_{2_{n}})%20+%20(1%20-%20t_n)%20&#x5C;log%20&#x5C;{%201%20-%20P(x_{1_{n}},%20x_{2_{n}})%20&#x5C;}]"/>

이렇게 해서 오차 함수가 식 (2.13)으로 완성되었다.

> **Note**: 로그함수를 취할 수 있는 이유는 우리가 찾는 것은 P의 구체적인 값이 아니라 P를 최대로 하는 것이기 때문이다. 로그함수는 단조 증가하는 함수이므로 P를 최대로 하는 것과 -logP를 최소로 하는 것은 동치가 된다.

## #


`#inProgress : p.56`

---

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


먼저 오차 함수는 파라미터에 대한 함수라는 것을 알아야 한다.
파라미터가 포함된 모델의 방정식이 오차 함수에 들어가 있다.
즉, **파라미터 값이 변경되면 오차 함수의 값도 변화하므로, 오차 함수는 파라미터에 대한 함수라고 볼 수 있다**.

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(1)%20&#x5C;%20L%20=%20&#x5C;frac{1}{2}&#x5C;Sigma(y_i%20-%20t_i)^{2}"/>

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(2)%20&#x5C;%20y_i%20=%20w_0%20+%20w_1x_1%20+%20w_2x_2%20+%20w_3x_3%20+%20w_4x_4%20=%20&#x5C;Sigma%20w_ix_i"/>

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(3)%20&#x5C;%20L(w_0,%20w_1,%20w_2,%20w_3,%20w_4)%20=%20&#x5C;frac{1}{2}&#x5C;Sigma(&#x5C;Sigma%20w_ix_i%20-%20t_i)^{2}"/>

#### 2) 오차 함수를 각 parameter로 편미분한 값을 0으로 두는 연립방정식을 푼다


오차 함수를 다변수 공간에 표현하면 함수값이 최소로 되는 최저점이 있을 것이다.
이 최저점은 기울기 벡터가 0이 되는 곳을 뜻한다.
기울기 벡터는 오차 함수를 각 parameter별로 편미분하면 구할 수 있다.
따라서 오차 함수를 편미분해서 기울기 벡터를 구하고 기울기 벡터가 0이 되는 곳을 찾으면, 오차 함수의 최소값을 구할 수 있게 된다.

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(4)%20&#x5C;%20&#x5C;frac{&#x5C;partial%20L}{&#x5C;partial%20w_i}(w_0,%20w_1,%20w_2,%20w_3,%20w_4)%20=%200"/>

이제 식 (3)의 값을 최소로 하는 <img src="https://latex.codecogs.com/gif.latex?w_0,%20w_1,%20w_2,%20w_3,%20w_4"/>의 값을 결정한다.
구체적으로는 식 (3)을 <img src="https://latex.codecogs.com/gif.latex?w_0,%20w_1,%20w_2,%20w_3,%20w_4"/> 각각으로 편미분한 값을 0으로 하는 다음과 같은 연립방정식을 푸는 것이다.
편미분하는 작업은 수학을 좋아하는 사람에게 숙제로 남겨 두고 여기서는 식 (4)의 조건으로 L이 최소가 되는 이유를 설명하겠다.

#### 3) "오차 함수의 편미분 = 0"으로 두면 오차 함수가 최소가 되는 이유


<img src="https://latex.codecogs.com/gif.latex?L(w_0,%20w_1,%20w_2,%20w_3,%20w_4)"/>와 같은 다변수 함수의 경우 편미분하면 어떻게 될까?
간단하게 설명하기 위해 2변수 함수의 편미분을 생각해보자.
편미분한 벡터를 식 (7)처럼 triangledown 기호로 나타내며, 함수 <img src="https://latex.codecogs.com/gif.latex?h(x_1,%20x_2)"/>이 '**기울기 벡터(gradient vector)**'라고 한다.

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(5)%20&#x5C;%20h(x_1,%20x_2)%20=%20&#x5C;frac{1}{4}(x_1^{2}%20+%20x_2^{2})"/>

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(6)%20&#x5C;%20&#x5C;frac{&#x5C;partial%20h}{&#x5C;partial%20x_1}%20=%20&#x5C;frac{1}{2}x_1,%20&#x5C;%20&#x5C;frac{&#x5C;partial%20h}{&#x5C;partial%20x_2}%20=%20&#x5C;frac{1}{2}x_2"/>

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(7)%20&#x5C;%20&#x5C;triangledown%20h(x_1,%20x_2)%20=%20&#x5C;begin{pmatrix}&#x5C;frac{1}{2}x_1%20&#x5C;&#x5C;&#x5C;frac{1}{2}x_2&#x5C;end{pmatrix}%20=%20&#x5C;frac{1}{2}%20&#x5C;begin{pmatrix}x_1%20&#x5C;&#x5C;x_2&#x5C;end{pmatrix}"/>

기울기 벡터에는 도형에서의 의미가 있다.
**기울기 벡터** <img src="https://latex.codecogs.com/gif.latex?&#x5C;triangledown%20h(x_1,%20x_2)"/>는 '**절구 벽면을 올라가는 방향과 일치**'하고, **기울기 벡터의 크기** <img src="https://latex.codecogs.com/gif.latex?||&#x5C;triangledown%20h(x_1,%20x_2)||"/>는 '**벽을 오르는 기울기와 일치**'한다.
절구 벽면의 기울기가 클수록 기울기 벡터도 길어지는 것이다.
따라서 임의의 점 <img src="https://latex.codecogs.com/gif.latex?(x_1,%20x_2)"/>에서 출발해서 기울기 벡터와 반대 방향으로 나아가면 절구의 벽면을 내려감과 동시에 기울기 벡터의 크기는 점점 작아진다.
최종적으로 원점 <img src="https://latex.codecogs.com/gif.latex?(0,0)"/>에 도달했을 때 <img src="https://latex.codecogs.com/gif.latex?h(x_1,%20x_2)"/>는 최소가 되고, 기울기 벡터의 크기도 0이 된다.

우리가 원하는 것은 여러 개의 변수를 포함하고 있는 오차 함수의 값을 최소화시키는 것이다.
그런데 성질을 파악해보니 오차 함수의 값이 최소가 될 때, 그 때 오차 함수의 기울기 벡터의 크기도 0이 되더라.
즉, 파라미터가 포함된 오차 함수 <img src="https://latex.codecogs.com/gif.latex?L%20=%20&#x5C;frac{1}{2}&#x5C;Sigma(&#x5C;Sigma%20w_ix_i%20-%20t_i)^{2}"/>을 최소로 하는 <img src="https://latex.codecogs.com/gif.latex?(w_0,%20w_1,%20w_2,%20w_3,%20w_4)"/>는 <img src="https://latex.codecogs.com/gif.latex?&#x5C;triangledown%20L(W)=0"/>으로 구해진다는 것이다.

`[inDetail]` 오차 함수를 시각화하면 <img src="https://latex.codecogs.com/gif.latex?(w_0,%20w_1,%20w_2,%20w_3,%20w_4)"/> 방향(=축)과 함수 값 <img src="https://latex.codecogs.com/gif.latex?L"/>축을 가진 그래프에서 하나의 도형으로 표현할 수 있다.
우리가 구해야 하는 값은 오차 함수의 최소값이므로, 오차 함수를 시각화한 그래프 상에서 함수 값 <img src="https://latex.codecogs.com/gif.latex?L"/>축이 가장 낮아지는 곳을 찾으면 된다.
<img src="https://latex.codecogs.com/gif.latex?L"/>축이 가장 낮아지는 곳은 곧 도형의 기울기 벡터의 크기가 0이 되는 곳과 같다.
즉 오차 함수의 최소값을 구하려면 오차 함수의 기울기 벡터가 0이 되는 것을 찾으면 된다.
다변수 함수에서 기울기 벡터는 편미분으로 구할 수 있다.
그리고 기울기 벡터는 <img src="https://latex.codecogs.com/gif.latex?&#x5C;triangledown%20L(W)"/> 기호로 나타낸다.
즉, 파라미터가 포함된 오차 함수 <img src="https://latex.codecogs.com/gif.latex?L%20=%20&#x5C;frac{1}{2}&#x5C;Sigma(&#x5C;Sigma%20w_ix_i%20-%20t_i)^{2}"/>을 최소로 하는 <img src="https://latex.codecogs.com/gif.latex?(w_0,%20w_1,%20w_2,%20w_3,%20w_4)"/>는 <img src="https://latex.codecogs.com/gif.latex?&#x5C;triangledown%20L(W)=0"/>으로 구할 수 있다.

#### 4) 경사 하강법


임의의 점 <img src="https://latex.codecogs.com/gif.latex?(x_1,%20x_2)"/>에서 출발해서 기울기 벡터와 반대 방향으로 나아가면 절구(=오차 함수의 도형 형태)의 벽면을 내려감과 동시에 기울기 벡터의 크기는 점점 작아진다.
우리가 찾는 오차 함수의 최저점은 기울기 벡터의 크기가 0이 되어야 한다.
따라서 기울기 벡터의 크기가 0이 되는 곳까지 현재 위치의 기울기 벡터와 반대 방향으로 반복해서 내려간다.

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(8)%20&#x5C;%20W^{new}%20=%20W%20-%20&#x5C;alpha%20&#x5C;triangledown%20L(W)"/>

    + <img src="https://latex.codecogs.com/gif.latex?W"/> : <img src="https://latex.codecogs.com/gif.latex?(w_0,%20w_1,%20w_2,%20w_3,%20w_4)"/>의 현재 위치(=좌표)
    + <img src="https://latex.codecogs.com/gif.latex?-%20&#x5C;triangledown%20L(W)"/> : 현재 위치 <img src="https://latex.codecogs.com/gif.latex?W"/>에서의 기울기 벡터와 반대방향으로 간다
    + <img src="https://latex.codecogs.com/gif.latex?-%20&#x5C;alpha%20&#x5C;triangledown%20L(W)"/> : 한 번 반대 방향으로 갈 때 <img src="https://latex.codecogs.com/gif.latex?&#x5C;alpha"/>만큼 이동한다
    + <img src="https://latex.codecogs.com/gif.latex?W^{new}"/> : 현재 위치에서 현재 위치에서의 기울기 벡터만큼 반대 방향으로 이동한 곳이 새로운 위치이다 (= 파라미터 갱신)

+ <img src="https://latex.codecogs.com/gif.latex?&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20&#x5C;%20(9)%20&#x5C;%20&#x5C;triangledown%20L(W)%20=%20&#x5C;begin{pmatrix}&#x5C;frac{&#x5C;partial%20L}{&#x5C;partial%20w_0}(W)%20&#x5C;&#x5C;&#x5C;vdots%20&#x5C;&#x5C;&#x5C;frac{&#x5C;partial%20L}{&#x5C;partial%20w_4}(W)&#x5C;end{pmatrix}"/>

이때 식 (8)에서 파라미터를 갱신할 때마다 그 점에서의 기울기 벡터 값을 식 (9)로 다시 계산한다는 점에 주의한다.
이렇게 현재 파라미터의 값에 대해 기울기 벡터를 계산하고, 그 반대 방향으로 파라미터를 수정하는 알고리즘을 '**경사 하강법(gradient descent**)'이라고 한다.
현실의 문제에서는 충분히 원점에 가까워졌을 때 계산을 중단하고, 그 시점의 값을 근사적인 최적해로 채택한다.
파라미터를 갱신하는 계산은 당연히 컴퓨터를 이용해 자동화하며, 이 부분이 머신러닝이나 딥러닝에서 텐서플로의 역할에 해당한다.
**training set의 양이 많은 경우 한 번에 모든 데이터를 이용해서 파라미터를 최적화하는 것이 아니라, 단계적으로 데이터를 투입해가면서 파라미터를 최적화해 가는 식의 테크닉도 필요하다**.

#### 5) 경사 하강법으로 풀리지 않는 문제


그런데 오차 함수의 그래프가 여러 곳에 local minima가 있다면 기울기 벡터가 0이 되는 곳이 여러 군데 존재하게 된다.
즉, 경사 하강법으로 global minimum에 도달하지 못할 수도 있다.
이와 같은 문제에 대응하기 위해 확률적 경사 하강법(SGD)이나 미니 배치(mini-batch) 같은 테크닉을 사용한다.

> **Note**: 2.3.4 미니배치와 확률적 경사 하강법

**끝.**

---
