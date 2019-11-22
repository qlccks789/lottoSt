# [lottoSt 로또 기반을 이용한 프로그램]

> #### Arguments 입력값 2종류
>> 1. LottoMaker 23,12,9,2,43,32 1:1,2:3,3:10,4:50,5:100 500       1~5등, 미등수가 순서대로 나옴</br>
>> 2. LottoMaker 23,12,9,2,43,32 1:1,2:3,3:10,4:50,5:100 500 TRUE : 1~5등, 미등수가 적절하게 섞여서 나옴
</br>

> #### [값 받는 순서]
>> 1. args[0] -> 23,12,9,2,13,1 (1등 숫자 받기)</br>
>> 2. args[1] -> 1:1,2:3,3:10,4:50,5:100 (로또 등수별 개수 받기 ex:3:10 -> 3등 10명)</br>
>> 3. args[2] -> 1000(로또 전체 수)</br>
>> 4. args[3] -> TRUE(정렬) 옵션</br>
</br>

> #### 1-1. [args lenght vaildation]
>> - args length < 3 이면 ERR
>> - args length > 3 args[3] 값 받기 - TRUE(정렬) 옵션값
</br>

> #### 1-2. [23,12,9,2,13,1 (1등 숫자 받기)]
>> - 받은 번호가 6개가 맞는지 - 넘으면 ERR
>> - 받은 번호에 중복숫자가 있는지 있으면 ERR
>> - 받은 번호가 숫자만 들어있는지 숫자외 문자가 들어있으면 ERR
>> - 받은 번호가 지정 범위안에 있는 숫자들로 구성되어 있는지 지정범위 초과된 숫자가 있을시 ERR
</br>

> #### 1-3. [1:1,2:3,3:10,4:50,5:100 (로또 등수마다 개수 받기)]
>> - :(colon) ,(comma)를 제외한 숫자만 들어오는지
>> - 1등은 1개, 2등은 0이상, 3등은 0이상, 4등은 0이상, 5등은 0이상(고정)
>> - 1등으로 구성된 번호 개수에 따라 생성 되는 등수 범위가 맞는지 
>>> ex 1) 1등번호가 7개로 구성(1,15,23,44,29,36,43) -> 1등 ~ 6등까지만 가능 7등 생성 불가 </br>
>>> ex 2) 1등번호가 6개로 구성(1,15,23,44,29,36) &nbsp;&nbsp;&nbsp; -> 1등 ~ 5등까지만 가능 6등 생성 불가 </br>
</br>

> #### 1-4. [100(총 로또 개수)]
>> - ,(comma)를 제외한 숫자만 들어오는지
>> - 1~5등의 개수가 총 개수보다 큰지
</br>

> #### 1-5. [1-3. TRUE(정렬) 옵션]
>> - "TRUE" 일때만 랜덤옵션 추가
</br>

> #### 2. [등수마다 로또 생성(미등수 포함)]
>> - set 사용(중복 검사)
>> - 1등번호 6개를 가지고와서 해당등수의 일치 개수만큼 줄인다. 3등이면 4개가 될때까지 뺀다.
</br>

> #### 3. [생성한 번호들을 리스트에 담는다]
>> - 생성한 행끼리 중복검사
</br>

> #### 4. [정렬할지 안할지 판단하고 출력]
