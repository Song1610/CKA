# Yaml Introduction 목차
- [Yaml Introduction 목차](#yaml-introduction-목차)
- [YAML-1](#yaml-1)
- [YAML-2](#yaml-2)
- [YAML-3](#yaml-3)
- [YAML-4](#yaml-4)
- [YAML-5](#yaml-5)
- [YAML-6](#yaml-6)
- [솔루션링크](#솔루션링크)
---

# YAML-1
food.yml 파일을 업데이트하여 'Vegetable: Carrot'을 추가하세요.

```yaml
Fruit: Apple
Drink: Water
Dessert: Cake
Vegetable: Carrot
```




# YAML-2
food.yml 파일을 업데이트하여 당근, 토마토, 오이 등 야채 목록을 추가하세요.

```yaml
Fruits:
  - Apple
  - Banana
  - Orange

Vegetables:
  - Carrot
  - Tomato
  - Cucumber
```




# YAML-3
food.yml 파일에 과일 영양 정보가 업데이트되었습니다. <br>
채소 영양 정보도 업데이트되었습니다. 자세한 내용은 아래 표를 참조하세요. <br>

|Vegetables|Calories|Fat|Carbs|
|:--:|:--:|:--:|:--:|
|Carrot|25|0.1|6|
|Tomato|22|0.2|4.8|
|Cucumber|8|0.1|1.9|


```yaml
Fruits:
  - Apple:
        Calories: 95
        Fat: 0.3
        Carbs: 25
  - Banana:
      Calories: 105
      Fat: 0.4
      Carbs: 27
  - Orange:
        Calories: 45
        Fat: 0.1
        Carbs: 11

Vegetables:
  - Carrot:
        Calories: 25
        Fat: 0.1
        Carbs: 6
  - Tomato:
      Calories: 22
      Fat: 0.2
      Carbs: 4.8
  - Cucumber:
        Calories: 8
        Fat: 0.1
        Carbs: 1.9
```




# YAML-4
제이콥은 **30세** **남성(Male)** 으로 회사에서 **시스템 엔지니어(Systems Engineer)** 로 일하고 있습니다. <br>
제이콥의 정보`(Name, Sex, Age, Title)`를 YAML 형식으로 표현하세요. <br>
`Employee`이라는 이름의 사전을 만들고 그 아래에 속성을 정의하세요.

```yaml
Employee:
  Name: Jacob
  Sex: Male
  Age: 30
  Title: Systems Engineer
```





# YAML-5
Jacob에게 할당된 **프로젝트(Projects)** 를 나타내도록 YAML 파일을 업데이트하세요. <br>
Jacob은 **자동화(Automation)** 및 **지원(Support)** 등 여러 프로젝트를 담당하고 있습니다. <br>
따라서 목록을 사용하는 것을 잊지 마세요.

```yaml
Employee:
  Name: Jacob
  Sex: Male
  Age: 30
  Title: Systems Engineer
  Projects:
    - Automation
    - Support
```





# YAML-6
야곱의 급여 명세서를 포함하도록 YAML 파일을 업데이트하세요. <br>
새 속성 **"급여 명세서"(Payslips)** 를 추가하고 급여 명세서 세부 정보 목록을 생성하세요(사전 목록 사용). <br>
각 급여 명세서 세부 정보에는 **월과 임금(Month and Wage)** 이 포함됩니다.

|Month|Wage|
|:--:|:--:|
|June|4000|
|July|4500|
|August|4000|

```yaml
Employee:
  Name: Jacob
  Sex: Male
  Age: 30
  Title: Systems Engineer
  Projects:
    - Automation
    - Support
  Payslips:
    - Month: June
      Wage: 4000
    - Month: July
      Wage: 4500
    - Month: August
      Wage: 4000
```



# 솔루션링크
https://github.com/mmumshad/kubernetes-training-answers