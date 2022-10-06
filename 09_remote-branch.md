# **:iphone: 원격 브랜치**
```PROPERTIES
협업을 위해서는 로컬 저장소에서 작업하고 원격 저장소에도 공유합니다.
```

## **:question: 리모트 브랜치란?**
원격 저장소에 생성한 브랜치를 **리모트 브랜치**라고 합니다.<br>
생성한 브랜치는 서버로 공유할 수 있습니다.<br>
- ### 브랜치를 새로 생성한 경우 저장소를 동기화해야 합니다.
    - 로컬저장소에서 새로운 브랜치를 생성한다고, 연결된 원격 저장소에 자동으로 브랜치가 생성되지 않습니다.<br>
    - 반대로 원격저장소에 등록된 브랜치가 자동으로 로컬저장소를 만들지 않습니다.
- ### 원격 및 로컬저장소의 이름은 보통 같습니다.
    - 서로 다른 이름으로 브랜치를 연결할 수 있습니다.
    - 두 저장소는 서로 다른 브랜치로 운영 • 관리 할 수 있습니다.
- ### 리모트 브랜치는 보통 `[별칭/브랜치]` 이름 형태입니다.

## **:wrench: 원격 브랜치 준비단계**

### **1. 실습 저장소를 생성해서 저장소 주소를 확인합니다.**<br>
반드시 본인의 계정으로 로그인합니다.

<kbd>
<img src="https://user-images.githubusercontent.com/45596014/193051781-80b82c60-1940-45fb-9419-ce0c5b57860e.jpg">
</kbd>
<kbd>
<img width="800" alt="image" src="https://user-images.githubusercontent.com/45596014/194218700-61f8d275-4e1a-491b-b656-4faaf8f85ea5.jpg">
</kbd>

<br>

### **2. 로컬저장소와 원격저장소를 연결합니다.**
<kbd>
<img src="https://user-images.githubusercontent.com/45596014/194304433-9f445569-2861-4535-b5c0-c3e3292940bd.jpg">
</kbd>

<br>

## **:compass: 브랜치 추적**
깃의 브랜치는 특정 커밋 해시 값을 가리키는 `포인터` 입니다.<br>
>※ 리모트 브랜치를 원격 브랜치라고 합니다.<br>
>※ 트래킹 브랜치를 추적 브랜치라고 합니다.
1. 원격저장소의 브랜치를 가리키는 것을 브랜치 추적이라고 합니다.<br>
2. 추적 브랜치는 원격 브랜치의 마지막 커밋 해시 값을 가리킵니다.<br>
    >※ 로컬저장소는 마지막으로 연결된 리모트 브랜치의 커밋 해시 값을 항상 가지고 있습니다.
3. 이 포인터 정보는 .git/refs 폴더 안에 저장되어 있습니다.<br>
4. 트래킹 브랜치는 원격 브랜치를 가리키는 북마크와 같습니다.<br>
5. 로컬저장소가 원격저장소와 연결될 때, 원격 브랜치의 트래킹 정보는 자동으로 갱신됩니다.<br>


<br>

## **:outbox_tray: 브랜치 업로드**
로컬저장소에만 브랜치를 생성했고, 이 브랜치는 원격저장소에 자동 등록되지 않습니다.
>※ 원격 저장소를 `등록`만 했기 때문에 아직 리모트 브랜치는 없습니다.<br>
>※ 리모트 브랜치는 서버간에 통신을 한 후에 생성됩니다.
### **1. 원격저장소 리모트 브랜치 확인**
```bash
$ git remote show origin # origin은 원격 브랜치명
```
<kbd>
<img src="https://user-images.githubusercontent.com/45596014/194318629-a7556176-0dfe-44fb-b084-84c95903eb18.jpg">
</kbd>

<br>

### **2. 원격저장소 동기화**
push를 하게되면 원격저장소는 로컬저장소와 동일한 branch를 생성하게 됩니다.
>※ 원격저장소는 첫 생성 시 브랜치가 없는 상태입니다.
```bash
$ git push origin main # origin은 원격저장소 별칭, main은 브랜치 이름
```
<img src="https://user-images.githubusercontent.com/45596014/194323234-b491f08f-6c72-42aa-8df4-05de24fb17c9.jpg">

### **3. 브랜치 확인**
2-1. 깃허브에서 해당 저장소의 브랜치를 확인합니다.

<kbd>
<img src="https://user-images.githubusercontent.com/45596014/194325158-aafa553a-4ac8-453e-b514-d4ed248a9665.jpg">
</kbd>

2-2. 다시 현재 로컬저장소의 브랜치를 확인합니다.

<kbd>
<img src="https://user-images.githubusercontent.com/45596014/194326239-ef53537f-ab9b-43bd-8aa7-2bee90c4dc81.jpg">
</kbd>

<br>

### **3. 브랜치 업로드**
원격저장소에 새로운 브랜치를 생성하려면 로컬저장소에서 브랜치 전송 명령을 실행해주어야 합니다.<br>
>※ 2번과 동일하며, 브랜치 이름만 변경합니다.
1. 브랜치 생성<br>
<kbd>
<img src="https://user-images.githubusercontent.com/45596014/194333677-2111d656-144f-407d-b3e1-2f3cceac1d88.jpg">
</kbd>

2. 브랜치 업로드<br>
<kbd>
<img src="https://user-images.githubusercontent.com/45596014/194334702-9ff209dd-1706-4b4d-8276-146093015658.jpg">
<img src="https://user-images.githubusercontent.com/45596014/194335536-47480706-3a05-47fb-bb89-c5c7ac388bf3.jpg">
</kbd>