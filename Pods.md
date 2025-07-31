# Pods
- [Pods](#pods)
- [Pods-1](#pods-1)
- [Pods-2](#pods-2)
- [Pods-3](#pods-3)
- [Pods-4](#pods-4)
- [Pods-5](#pods-5)
- [Pods-6](#pods-6)
- [Pods-7](#pods-7)
- [Pods-8](#pods-8)
- [Pods-9](#pods-9)

---

# Pods-1
`pd-definition.yml`에 `apiVersion`과 `kind`라는 두 개의 루트 수준 속성을 추가

지침: 누락된 두 속성(`metadata`와 `spec`)을 추가합니다.

```yaml
apiVersion: 
kind:
metadata:
spec:
```



# Pods-2
소개: 속성 값 채우기

지침: `apiVersion` 값을 `v1`로 업데이트합니다. <br>
콜론(:)과 값(v1) 사이에 공백을 추가해야 합니다.

```yaml
apiVersion: v1
kind:
metadata:
spec:
```



# Pods-3
지침: kind에 `Pod` 추가 <br>

```yaml
apiVersion: v1
kind: Pod
metadata:
spec:
```




# Pods-4
지침: 메타데이터 아래에 `"name"` 속성을 추가하고 값은 `"myapp-pod"`입니다. <br>
'name' 앞에 공백을 추가하여 메타데이터의 자식으로 만드세요. 

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
spec:
```




# Pods-5
소개: Pod에 레이블을 추가

지침: 메타데이터 아래에 `"labels"` 속성을 추가하고, 자식 속성 `"app"`과 `"myapp"` 값을 가집니다. <br>
"name"과 "labels" 앞에 같은 개수의 공백을 두어 형제 관계를 유지해야 합니다.

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
  labels:
    app: myapp
spec:
```




# Pods-6
소개: 도커 이미지 정보 제공

지침: `spec` 섹션 아래에 `"containers"` 속성을 추가합니다.

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
  labels:
    app: myapp
spec:
  containers:
```



# Pods-7
지침: Containers는 `array/list`입니다. <br>
따라서 array/list의 첫 번째 `element/item`을 만들고 다음 속성을 추가합니다. <br>
```
name - nginx
image - nginx
```


```yaml
apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
  labels:
    app: myapp
spec:
  containers:
    - name: nginx
      image: nginx
```




# Pods-8
지침: 아래 값을 사용하여 Kubernetes Pod 정의 파일을 생성합니다.

- Name: postgres 
- Labels: tier => db-tier
- Container name: postgres
- Image: postgres 

<br>

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: postgres
  labels:
    tier: db-tier
spec:
  containers:
    - name: postgres
      image: postgres
```




# Pods-9
소개: `Postgres Docker` 이미지에는 비밀번호로 설정할 `환경 변수`가 필요합니다.

지침: Docker 컨테이너의 환경 변수를 설정합니다. `POSTGRES_PASSWORD`에 `mysecretpassword` 값을 지정합니다. <br>
강의에서 다루지는 않았지만 간단합니다. <br>
환경 변수를 전달하려면 컨테이너 객체에 새 속성 `'env'`를 추가합니다. <br>
이 속성은 `image`와 `name`의 형제입니다. <br>
env는 배열/리스트입니다. 따라서 그 아래에 새 항목을 추가합니다. <br>
해당 항목에는 `name`과 `value` 속성이 있습니다. <br>
name은 환경 변수의 이름인 POSTGRES_PASSWORD여야 하고, value는 비밀번호인 mysecretpassword여야 합니다.


```yaml
apiVersion: v1
kind: Pod
metadata:
  name: postgres
  labels:
    tier: db-tier
spec:
  containers:
    - name: postgres
      image: postgres
      env:
        - name: POSTGRES_PASSWORD
          value: mysecretpassword
```