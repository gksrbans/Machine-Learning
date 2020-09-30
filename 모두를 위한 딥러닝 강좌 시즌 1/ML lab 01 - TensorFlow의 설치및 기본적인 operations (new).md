# Tensorflow
- Python 기반의 deeplearning Framework.
- data flow graphs를 사용한 연산(?)
- 열심히 해야딩

### Data Flow Graph?
- data 연산이 일어나는 flow들을 지칭함.
- tensor가 돌아다닌다! tensorflow


### install
- python -m pip install --upgrade
- pip install --upgrade tensorflow
- python 3.6버전 이하만 됨...
- 나는 코랩에서 할거라능!
```sh
import tensorflow as tf
tf.__version__
```

### Tensorflow Hello World!
- 강의가 구버전이라 Tensorflow 1.X버전의 문법을 따른다.
- 코랩 내 tensorflow 버전에 맞게 사용
```sh
import tensorflow as tf
# tf.__version__


hello = tf.constant("Hello, Tensorflow 규무닝!")
#sess = tf.Session()
#print(sess.run(hello))
tf.print(hello)
```

### Computational Graph
- 노드의 연결을 실습해보자 (간단한 노드끼리의 더하기 연산.)
```sh
import tensorflow as tf
# tf.__version__

node1 = tf.constant(3.0, tf.float32)
node2 = tf.constant(4.0)
node3 = tf.add(node1, node2)

print("node1:", node1, "node2:", node2)
print("node3: ", node3)
```
> 출력 시 tensor의 형태와 모양이 나오지 결과 값이 출력되지 않음.

- 결과값 출력 하는법
```sh
import tensorflow as tf
# tf.__version__

node1 = tf.constant(3.0, tf.float32)
node2 = tf.constant(4.0)
node3 = tf.add(node1, node2)

# print("node1:", node1, "node2:", node2)
# print("node3: ", node3)
tf.print(node1, node2)
tf.print(node3)
```
> tensorflow 2.X 부터는 session을 정의하고 Run하는게 생략됨.

### Placeholder
- placeholder 역시 Tensorflow 1.X에서 쓰이며, @tf.function 데코레이터 삽입을 통해 기존 파이썬 함수 작성하듯이 사용 가능함
```sh
import tensorflow as tf
# tf.__version__

# a = tf.placeholder(tf.float32)
# b = tf.placeholder(tf.float32)
# adder_node = a + b

# tf.print(feed_dict={a:3, b:4.5})
# Placeholder 역시 tensorflow 1.X에서 쓰임

@tf.function
def kyum_add(a, b):
  return a + b

a = tf.constant(3)
b = tf.constant(4)

tf.print(kyum_add(a,b))
```
