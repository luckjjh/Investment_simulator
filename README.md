# Investment_simulator
1. Investment_simulator_2016742039.java 파일에 있는 main method를 활용해 간단한 모의 주식을 할 수 있는 프로그램입니다.

2. 개요
1) 간단한 모의 주식을 체험해 볼 수 있는 프로그램입니다.

2) 누구나 알 만한 총 10개 기업의 주식(Samsung, Apple, Naver, AMD, Microsoft, TESLA, LG, NVIDIA, Kakao, Huawei)의 주가를 임의로 설정하였고, 10개의 주식들을 초기에 입력하는 자본금을 통해 구매/판매를 해 최종적으로 수익을 내는 것이 목표인 모의 주식 투자 프로그램입니다.

3) 모든 기업의 주가는 하루가 지나면 랜덤으로 정해지는 등락률에 따라 주가가 오르거나 내려갑니다. 이를 이용해 주식을 구매/판매하는 타이밍을 잘 잡아 수익을 내면 됩니다. 수익률은 최대 30% 증가 할 수 있고 
최소 -25% 감소 할 수 있습니다.

4) 프로그램은 정수형 숫자(0~9)로 동작을 제어할 수 있습니다. 

5) 프로그램 동작 숫자로 ‘0’을 입력해 중간에 프로그램을 종료하지 않는 다면 최대 30일 동안 모의 주식 투자를 할 수 있도록 제한했습니다.

6) 프로그램을 실행할 수 있는 main method는 Investment_simulator_2016742039.java 파일이고 추가로 3개의 class 와 1개의 implement 파일을 갖고있습니다.

7) 올바르지 않은 입력이 들어올 경우 프로그램이 Error 구문을 출력하고 종료될 수 도 있습니다.
Ex) 초기 자산을 입력해야 하는데 음수, 문자열로 입력하는 경우

3. 기능 소개
프로그램은 제일 먼저 ID(문자열), 초기 자본(정수형)을 입력 받아야 시작이 됩니다.
사용자의 ID와 초기자본을 입력 받은 후에는 0~9까지의 수를 이용해 동작을 제어합니다.
1-현재 보유 주식현황(총 자산현황) 확인 (자신의 총 자산과 보유하고 있는 주식의 개수를 출력하는 기능) ,
2-금일 주가 확인 (각 기업별로 주가를 출력해 주는 기능) ,
3-금일 주가 오름차순으로 확인 , 4-금일 주가 내림차순으로 확인 ,
5-주식 구매(구매하려는 주식의 이름과 개수를 입력하고 현재 가격으로 주식을 구매), 6-주식 판매(판매하려는 주식의 이름과 개수를 입력하고 현재 가격으로 주식을 판매) ,
7-주식 등락률 차트로 확인(차트를 확인할 주식을 입력 받고 차트를 세로로 출력) ,
8-기업 정보 확인(정보를 확인할 주식을 입력 받고 기업의 정보 출력) ,
9-다음날로 넘기기(날짜가 1 증가하고 주가 갱신) 
0-프로그램 종료
위와 같은 숫자 입력으로 프로그램의 동작을 제어 할 수 있습니다.

4. 프로그램 구성
1) Investment_simulator_2016742039.java
Main method가 있는 investment_simulator_2016742039.java 파일은 한 개의 main method가 존재하고 이 파일에서 프로그램을 실행 시킬 수 있습니다. Main method는 stock class로 이뤄진 collection framework인 list에 주식에 대한 정보를 입력하고 사용자의 입력을 switch case문으로 입력을 받고 제어를 합니다.

2) MyAccount.java
MyAccount class는 사용자의 정보를 관리하는 객체로 사용자의 이름(name), 자산(Property),보유주식(myAccountMap)등.. 이 선언되어 있습니다. Member method 로는 생성자인 MyAccount와 현재 자신의 정보인 이름, 예수금, 총 보유 자산, 보유 주식 개수를 출력하는 showMyInform(), 총 자산을 계산해서 반환하는 getAllProperty()와 최종적으로 수익률을 확인하는 showMyGain()이 있습니다. 그리고 Getter interface로 정의된 getName과 getValue도 overriding 되어 선언이 되어있습니다.

3) Stock.java
Stock class 가 담겨져 있고, 각 기업의 주식에 대한 정보가 담겨있는 객체입니다. member variable로는 주식의 이름(name), 가격(companyValue), 등락률(updownRate)이 선언되어 있습니다. Member method로는 Default 생성자와 인자를 받는 생성자 두개가 존재합니다. 그리고 주식의 정보를 갱신 할 수 있는 updateStock()와 주식의 정보를 출력하는 showTodayValue(), 주식의 등락률을 반환하는 getUpdownRate()가 선언 되어있습니다. 또한 그리고 Getter interface로 정의된 getName과 getValue도 overriding 되어 선언이 되어있습니다. 그리고 ReadPropertyException 이라는 자산이 입력될 때 음수로 입력이 되는 경우 예외를 처리할 class 도 정의가 되어 있습니다.

4) StockMarket.java
프로그램을 실행할 때 동작을 제어하기 위한 method들이 담겨있는 객체 StockMarket이 있는 파일입니다. 주식을 사거나 팔수 있는 metho인 buyStock, sellStock와 같은 method들이 존재하고, 차트를 출력하거나 회사의 정보를 출력하는 showCompanyInform, showChart 와 같은 method가 존재합니다. showCompanyInfrom은 열거형 값을 활용해 코딩했습니다.

5) Getter.java
값을 반환하기 위한 추상 method를 갖고 있는 Getter interface가 담겨 있습니다.

5. 사용방법(테스트 방법)
1) 프로그램을 실행한 후 입력 창에 자기 자신의 이름(ID)와 초기 자산을 입력합니다. (초기 자산은 100,000원 정도를 추천합니다.)

2) 입력을 마치면 프로그램이 실행되고 0~9까지의 입력을 통해 어떠한 동작을 할지 선택하고 입력하면 해당 동작을 할 수 있습니다. (※주의 0~9까지 입력이 아니지만 정수 형인 경우는 다시 입력 값을 받지만, 입력이 정수형이 아닌 경우 program이 종료됩니다.)

3) 1~4의 입력이 들어오면 해당 입력에 따라 출력 값이 출력됩니다.

4) 5, 6 입력이 들어오면 구매/판매할 주식의 이름을 입력하고 개수를 입력하면 해당 동작을 수행합니다. (기업 이름의 경우 대소문자 구분 없어도 가능합니다. / 없는 주식을 팔거나 예수금이 부족한데 주식을 구매할 경우 입력창으로 돌아갑니다.) / 5,6 입력을 해 주식을 구매/판매하기 전에 어떤 주식이 얼마인지 2, 3, 4입력으로 확인하고 구매하는 것을 추천합니다.

5) 7, 8 입력이 들어오면 기업명을 입력하고 입력한 기업에 대한 정보가 출력됩니다. (8번 입력 같은 경우 대소문자를 구분해 입력해 주셔야 합니다.)

6) 9번 입력이 들어오면 날짜가 갱신되고 모든 주식의 가격이 등락률에 따라 업데이트 됩니다.

7) 0번 입력을 하거나 날짜가 30일차가 지나면 프로그램이 종료되고 최종 수익률이 출력됩니다.

간단한 모의주식을 할 수 있는 프로그램 / program can do simple investment simulation
