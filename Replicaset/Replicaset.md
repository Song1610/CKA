# ReplicaSet 목차
- [ReplicaSet 목차](#replicaset-목차)
- [ReplicaSet-1](#replicaset-1)
- [ReplicaSet-2](#replicaset-2)
- [ReplicaSet-3](#replicaset-3)
- [ReplicaSet-4](#replicaset-4)
- [ReplicaSet-5](#replicaset-5)
- [ReplicaSet-6](#replicaset-6)
- [ReplicaSet-7](#replicaset-7)
---

# ReplicaSet-1
- 지침: 모든 루트 수준 속성을 추가합니다.
- 참고: 아직 속성만 추가하고 값은 추가하지 마세요.

```yaml
apiVersion: 
kind: 
metadata:
spec:
```


# ReplicaSet-2
- 소개: 이제 ReplicaSet에 값을 추가해 보겠습니다. ReplicaSet은 apiVersion - apps/v1에 있습니다.
- 지침: apiVersion 및 kind 값을 업데이트합니다.

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
spec:
```


# ReplicaSet-3
- 소개: 이제 메타데이터 값을 추가해 보겠습니다.
- 지침: ReplicaSet의 이름을 frontend로 지정합니다. 그리고 app=>mywebsite, tier=>frontend 라벨을 추가합니다.

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: mywebsite
    tier: frontend
spec:
```


# ReplicaSet-4
- 소개: 이제 사양에 대해 알아보겠습니다.
- 지침: ReplicaSet의 사양 섹션에는 복제본, 템플릿, 선택자(replicas, template and selector.)라는 세 가지 필드가 있습니다. 이 속성들을 추가하기만 하면 됩니다. 아직 값을 추가하지 마세요.

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: mywebsite
    tier: frontend
spec:
  selector:
  replicas: 
  template:
```


# ReplicaSet-5
- Instruction: Let us update the number of replicas to 4.

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: mywebsite
    tier: frontend
spec:
  replicas: 4
  template:
  selector:
```

# ReplicaSet-6
- 소개: 템플릿 섹션은 Pod 정의를 필요로 합니다. 다행히 이전 연습에서 만든 Pod 정의가 있습니다. 이제 replicaset-definition.yml 옆에 이전에 만든 것과 동일한 pod-definition.yml 파일이 있습니다.
- 지침: 이제 apiVersion과 kind를 제외한 pod-definition.yml 파일의 내용을 복사하여 템플릿 섹션 아래에 배치합니다. 템플릿 아래에 오도록 내용을 오른쪽으로 이동할 때는 특히 주의하세요.

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: mywebsite
    tier: frontend
spec:
  replicas: 4
  template:
    metadata:
      name: myapp-pod
      labels:
        app: myapp
    spec:
      containers:
        - name: nginx
          image: nginx
  selector:
```


pod-definition.yaml <br>

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


# ReplicaSet-7
- 소개: 이제 선택자를 업데이트하여 파드를 ReplicaSet에 연결해 보겠습니다.
- 지침: 선택자 아래에 "matchLabels" 속성을 추가하고 그 아래 파드 정의에 정의된 레이블을 복사합니다.
- 참고: 이 방법은 쿠버네티스 1.8 버전에서 실행되므로 play-with-k8s에서는 작동하지 않을 수 있습니다. ReplicaSet은 쿠버네티스 1.9 버전에서 apps/v1로 이동되었습니다.

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: mywebsite
    tier: frontend
spec:
  replicas: 4
  template:
    metadata:
      name: myapp-pod
      labels:
        app: myapp
    spec:
      containers:
        - name: nginx
          image: nginx
  selector:
    matchLabels:
      app: myapp
```