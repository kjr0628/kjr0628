<div align='center'>
  <img src="https://capsule-render.vercel.app/api?type=waving&fontColor=48648a&height=150&section=header&text=PEN%20CRAFT&fontSize=40&desc=Smart%20Factory&descAlignY=70&descAlign=50"/>
  <h3>🖍보드마카 생산 공장🖍</h3>
  <h4>☑ 제품별 품질 관리</h4>
  <h4>☑ 라인 내 에러 정보 통합 모니터링</h4>
  <h4>☑ 분석 시스템 구축</h4>
</div>

## 📞0. 목차
1. [프로젝트 소개](#1)
2. [개발 일정](#2)
3. [개발 환경 / Dependencies / 기술 스택](#3)
4. [담당 업무](#4)
5. [프로젝트 폴더 구조](#5)
6. [주요 기능 소개](#6)
7. [핵심 코드](#7)
8. [트러블 슈팅](#8)
9. [리팩토링 완료](#9)
10. [보완 사항](#10)
11. [보완 완료](#11)
12. [느낀 점 및 아쉬운 점](#12)
<br><br><br><br>
<span id="1"></span>
## 🏭1. 프로젝트 소개
해당 프로젝트는 5명의 인원으로 제품별 품질 관리와 라인 내 에러 정보 통합 모니터링 및 분석 시스템 구축이라는 스마트 팩토리의 주제를 선정하였을 때 실제 공장에서 일을 해본 적 경험이 없는 저희로서는 생각했을 때 직관적이고 단순하게 생각할 수 있는 보드마카를 생산하는 공장을 선정하였습니다.
저희의 프로젝트에서는 제품을 생산하는 4가지의 공정이 있고, 생산 지시가 내려졌을 때 1공정부터 4공정까지 진행이 되었을 때 각 공정마다 일정 시간이 지난 뒤 그래프를 통해 양품과 불량품의 개수가 보일 수 있도록 모니터링을 할 수 있게 하고 생산된 제품들은 품질 관리 페이지에서 제품별 품질 관리를 할 수 있는 기능을 가지고 있습니다. 생산되는 현황을 확인하고 생산된 제품의 품질을 관리할 수 있는 PEN CRAFT 프로젝트의 완성 과정을 소개해드리겠습니다.
<br><br><br><br>
<span id="2"></span>
## 📆2. 개발 일정
#### [2024.02.19 ~ 2024.03.15]
![개발일정](https://raw.githubusercontent.com/calmnature/pencraft/main/GIF/%EA%B0%9C%EB%B0%9C%EC%9D%BC%EC%A0%95.png)
<br><br><br><br>

<span id="3"></span>
## ⚙3. 개발 환경 / Dependencies / 기술 스택
### 🛠개발환경
  - **OS : Windows 10**
  - **통합개발환경(IDE) : IntelliJ**
  - **JDK Version : JDK 17**
  - **Database : MySQL**
  - **Build Tool : IntelliJ IDEA**

### 🖥Dependencies
  - **Spring Web**
  - **Spring Data JPA**
  - **Spring Boot DevTools**
  - **WebSocket**
  - **Lombok**
  - **Mysql Driver**
  - **Thymeleaf**

### ✏기술 스택
  - **Front End**<br>
![HTML](https://img.shields.io/badge/HTML-239120?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-239120?&style=for-the-badge&logo=css3&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white)
![Javascript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=JavaScript&logoColor=white)
![jQuery](https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white)
![Thymeleaf](https://img.shields.io/badge/Thymeleaf-239120?style=for-the-badge)
  - **Back End**<br>
![Spring](https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white)
![WebSocket](https://img.shields.io/badge/WebSocket-red?style=for-the-badge)
![JPA](https://img.shields.io/badge/JPA-DB7093?style=for-the-badge)
  - **Database**<br>
![MySQL](https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white)
![Woekbench](https://img.shields.io/badge/MySQL%20Workbench-00000F?style=for-the-badge&logo=mysql&logoColor=white)
  - **Communication**<br>
![Notion](https://img.shields.io/badge/Notion-000000?style=for-the-badge&logo=notion&logoColor=white)
![Discord](https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white)
<br><br><br><br>

<span id="4"></span>
## ✋4. 담당 업무
#### [담당 업무]
<br><br><br><br>

<span id="5"></span>
## 🗂5. 프로젝트 폴더 구조
```
📁src
┣ 📂main
┃ ┣ 📂java
┃ ┃ ┣ 📂com.example.pencraft
┃ ┃ ┃ ┣ 📂config
┃ ┃ ┃ ┃ ┣ 📄WebConfig.java                  // 필터 순서 설정 파일
┃ ┃ ┃ ┃ ┗ 📄WebSocketConfig.java            // 웹 소켓 설정 파일
┃ ┃ ┃ ┣ 📂constant
┃ ┃ ┃ ┃ ┗ 📄SessionConst.java               // 섹션에 저장할 로그인 이름 상수 선언
┃ ┃ ┃ ┣ 📂controller
┃ ┃ ┃ ┃ ┣ 📄EmployeesController.java        // 회원 관련 컨트롤러
┃ ┃ ┃ ┃ ┣ 📄ErrorController.java            // 에러 페이지 발생 컨트롤러
┃ ┃ ┃ ┃ ┣ 📄HomeController.java             // 로그인 성공 후 메인 페이지 컨트롤러
┃ ┃ ┃ ┃ ┣ 📄LoginController.java            // 로그인 컨트롤러
┃ ┃ ┃ ┃ ┣ 📄LotController.java              // Lot 관리 컨트롤러
┃ ┃ ┃ ┃ ┣ 📄ProcessController.java          // 생산 지시 컨트롤러
┃ ┃ ┃ ┃ ┣ 📄ProductController.java          // 제품 조회 컨트롤러
┃ ┃ ┃ ┃ ┗ 📄WebSocketController.java        // 웹 소켓 컨트롤러
┃ ┃ ┃ ┣ 📂domain
┃ ┃ ┃ ┃ ┣ 📄BaseTimeEntity.java             // Lot 생성 시 생성, 수정 시각 저장할 클래스 파일(상속 받아 사용)
┃ ┃ ┃ ┃ ┣ 📄Employees.java                  // 회원 Entity
┃ ┃ ┃ ┃ ┣ 📄Error.java                      // 생산 제품 에러 Entity
┃ ┃ ┃ ┃ ┣ 📄Lot.java                        // Lot Entity
┃ ┃ ┃ ┃ ┣ 📄OccurrenceError.java            // Lot 발생 에러 Entity
┃ ┃ ┃ ┃ ┣ 📄Process.java                    // 공정 Entity
┃ ┃ ┃ ┃ ┣ 📄Product.java                    // 제품 Entity
┃ ┃ ┃ ┃ ┗ 📄Standard.java                   // 제품 규격 Entity
┃ ┃ ┃ ┣ 📂filter
┃ ┃ ┃ ┃ ┣ 📄LogFilter.java                  // 모든 페이지 필터
┃ ┃ ┃ ┃ ┣ 📄LoginCheckFilter.java           // 비로그인 시 접근 가능 페이지 필터
┃ ┃ ┃ ┃ ┗ 📄RoleCheckFilter.java            // 로그인 후 관리자 및 일반 사용자 필터
┃ ┃ ┃ ┣ 📂form
┃ ┃ ┃ ┃ ┣ 📄CountForm.java                  // 생산 지시 DTO
┃ ┃ ┃ ┃ ┣ 📄EmployeesForm.java              // 회원 DTO
┃ ┃ ┃ ┃ ┣ 📄LastDataForm.java               // 모니터링 접속 시 가장 마지막에 생산된 양품, 불량품을 보낼 DTO
┃ ┃ ┃ ┃ ┣ 📄LoginForm.java                  // 로그인 시 사용할 Validation의 Form
┃ ┃ ┃ ┃ ┣ 📄LotCountForm.java               // 로그인 성공 후 메인 페이지에서 일/월/년별 그래프를 그리기 위한 DTO
┃ ┃ ┃ ┃ ┣ 📄LotForm.java                    // Lot DTO
┃ ┃ ┃ ┃ ┣ 📄PassFailProductForm.java        // Lot 관리 상세보기 시 각 공정의 양,불 개수를 보여주기 위한 DTO
┃ ┃ ┃ ┃ ┗ 📄ProductForm.java                // 제품 DTO
┃ ┃ ┃ ┣ 📂repository
┃ ┃ ┃ ┃ ┣ 📄EmployeesRepository.java        // 회원 Repository
┃ ┃ ┃ ┃ ┣ 📄ErrorRepository.java            // 에러 Repository
┃ ┃ ┃ ┃ ┣ 📄LotRepository.java              // Lot Repository
┃ ┃ ┃ ┃ ┣ 📄ProcessRepository.java          // 공정 Repository(미사용)
┃ ┃ ┃ ┃ ┣ 📄ProductRepository.java          // 제품 Repository
┃ ┃ ┃ ┃ ┗ 📄StandardRepository.java         // 제품 규격 Repository
┃ ┃ ┃ ┗ 📂service
┃ ┃ ┃ ┃ ┣ 📄EmployeesService.java           // 회원 Service
┃ ┃ ┃ ┃ ┣ 📄ErrorService.java               // 에러 Service
┃ ┃ ┃ ┃ ┣ 📄LoginService.java               // 로그인 Service
┃ ┃ ┃ ┃ ┣ 📄LotService.java                 // Lot Service
┃ ┃ ┃ ┃ ┣ 📄ProcessService.java             // 생산 지시 Service
┃ ┃ ┃ ┃ ┣ 📄ProductService.java             // 제품 Service
┃ ┃ ┃ ┃ ┣ 📄StandardService.java            // 규격 Service
┃ ┃ ┃ ┃ ┗ 📄WebSocketSenderService.java     // 서버 -> 클라이언트에게 메세지를 보내기 위한 Service
┃ ┃ ┃ ┣ 📄DummyDataLoader.java              // 서버 최초 실행 시 DB에 더미데이터를 넣기 위한 클래스 파일
┃ ┃ ┃ ┗ 📄PencraftApplication.java
┃ ┗ 📂resource
┃ ┃ ┣ 📂static
┃ ┃ ┃ ┣ 📂css
┃ ┃ ┃ ┃ ┣ 📄bootstrap.css                   // 부트스트랩 CSS
┃ ┃ ┃ ┃ ┣ 📄jumbotron-narrow.css
┃ ┃ ┃ ┃ ┣ 📄loginhome.css                   // 로그인 성공 후 관리자, 일반 사용자의 메인 페이지의 CSS
┃ ┃ ┃ ┃ ┣ 📄navbar.css                      // navbar.html의 CSS
┃ ┃ ┃ ┃ ┗ 📄style.css
┃ ┃ ┃ ┣ 📂img
┃ ┃ ┃ ┗ 📂js
┃ ┃ ┃ ┃ ┣ 📄home.js                         // SockJS를 연결하여 메인 페이지의 일/월/년별 데이터를 ChartJS로 그릴 JS 파일
┃ ┃ ┃ ┃ ┣ 📄monitoring.js                   // SockJS를 연결하여 모니터링 페이지에서 실시간 공정 생산 현황의 데이터를 ChartJS로 그릴 JS 파일
┃ ┃ ┃ ┃ ┗ 📄productShow.js                  // 제품 조회 페이지 '수정' 버튼 누를 경우 모달에서 데이터를 보여주기 위한 JS 파일
┃ ┃ ┣ 📂templates
┃ ┃ ┃ ┣ 📂employees
┃ ┃ ┃ ┃ ┣ 📄change_password.html            // 비밀번호 변경 시 현재 비밀번호를 입력하여 사용자를 확인하기 위한 뷰 페이지
┃ ┃ ┃ ┃ ┣ 📄create_employee.html            // 회원 생성 시 회원을 만들기 위한 뷰 페이지
┃ ┃ ┃ ┃ ┣ 📄input_password.html             // 현재 비밀번호 확인 후 새 비밀번호를 입력받기 위한 뷰 페이지
┃ ┃ ┃ ┃ ┗ 📄show_employee_list.html         // 회원 목록을 보여주기 위한 뷰 페이지
┃ ┃ ┃ ┣ 📂error
┃ ┃ ┃ ┃ ┣ 📄4xx.html                        // 400번대 에러 시 보여줄 뷰 페이지
┃ ┃ ┃ ┃ ┣ 📄5xx.html                        // 500번대 에러 시 보여줄 뷰 페이지
┃ ┃ ┃ ┃ ┗ 📄goBack.html                     // 일반 사용자가 관리자 페이지에 접속 시 보여 줄 뷰 페이지
┃ ┃ ┃ ┣ 📂fragment                          // 템플릿화를 하기 위한 폴더
┃ ┃ ┃ ┃ ┣ 📄bodyheader.html
┃ ┃ ┃ ┃ ┣ 📄header.html
┃ ┃ ┃ ┃ ┣ 📄navbar.html
┃ ┃ ┃ ┃ ┗ 📄pageup.html
┃ ┃ ┃ ┣ 📂lot
┃ ┃ ┃ ┃ ┣ 📄show_lot.html                    // Lot 관리를 보여줄 뷰 페이지
┃ ┃ ┃ ┃ ┗ 📄show_lot_detail.html             // Lot 관리 상세보기 버튼을 클릭 시 보여줄 뷰 페이지
┃ ┃ ┃ ┣ 📂products
┃ ┃ ┃ ┃ ┣ 📄error_products.html              // 불량품의 제품을 보여줄 뷰 페이지
┃ ┃ ┃ ┃ ┣ 📄monitoring.html                  // 생산 지시 후 실시간 생산 현황을 보여줄 뷰 페이지
┃ ┃ ┃ ┃ ┣ 📄show_products.html               // 생산된 제품을 보여줄 뷰 페이지
┃ ┃ ┃ ┃ ┗ 📄start_process.html               // 생산 지시의 뷰 페이지(규격, 수량 입력)
┃ ┃ ┃ ┣ 📂teams
┃ ┃ ┃ ┃ ┗ 📄teamlist.html                    // 팀원 리스트의 뷰 페이지
┃ ┃ ┃ ┣ 📄home.html                          // 최초 로그인 전 보여줄 뷰 페이지
┃ ┃ ┃ ┣ 📄loginAdminHome.html                // 로그인 성공 후 관리자가 볼 메인 페이지
┣ ╋ ╋ ┷ 📄loginStaffHome.html                // 로그인 성공 후 사용자가 볼 메인 페이지
┗ ┷ ┷ 📄application.properties
```
<br><br><br><br>

<span id="6"></span>
## 🔍6. 주요 기능 소개
|                                                로그인                                                 |                                                회원 생성 및 조회                                                 |
| :-----------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------: |
| ![로그인](https://raw.githubusercontent.com/calmnature/pencraft/main/GIF/1.%EB%A1%9C%EA%B7%B8%EC%9D%B8.gif) | ![회원생성](https://github.com/calmnature/pencraft/blob/main/GIF/2.%ED%9A%8C%EC%9B%90%20%EC%83%9D%EC%84%B1%20%EB%B0%8F%20%EC%A1%B0%ED%9A%8C.gif?raw=true) |

|                                                비밀번호 변경                                                 |                                                비밀번호 초기화                                                 |
| :-----------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------: |
| ![비밀번호 변경](https://raw.githubusercontent.com/calmnature/pencraft/main/GIF/3.%EB%B9%84%EB%B0%80%EB%B2%88%ED%98%B8%20%EB%B3%80%EA%B2%BD.gif) | ![비밀번호 초기화](https://raw.githubusercontent.com/calmnature/pencraft/main/GIF/4.%EB%B9%84%EB%B0%80%EB%B2%88%ED%98%B8%20%EC%B4%88%EA%B8%B0%ED%99%94.gif) |

|                                                회원 삭제                                                 |                                                일/월/년 그래프                                                 |
| :-----------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------: |
| ![회원 삭제](https://raw.githubusercontent.com/calmnature/pencraft/main/GIF/5.%ED%9A%8C%EC%9B%90%20%EC%82%AD%EC%A0%9C.gif) | ![일/월/년 그래프](https://raw.githubusercontent.com/calmnature/pencraft/main/GIF/6.%EC%9D%BC%EC%9B%94%EB%85%84%EA%B7%B8%EB%9E%98%ED%94%84.gif) |

|                                                생산 지시 및 중단                                                 |                                                제품 조회 및 수정                                                 |
| :-----------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------: |
| ![생산 지시 및 중단](https://raw.githubusercontent.com/calmnature/pencraft/main/GIF/7.%EC%83%9D%EC%82%B0%20%EC%A7%80%EC%8B%9C%20%EB%B0%8F%20%EC%A4%91%EB%8B%A8.gif) | ![제품 조회 및 수정](https://raw.githubusercontent.com/calmnature/pencraft/main/GIF/8.%EC%A0%9C%ED%92%88%20%EC%A1%B0%ED%9A%8C%20%EB%B0%8F%20%EC%88%98%EC%A0%95.gif) |

|                                                에러 조회                                                 |                                                Lot 조회                                                 |
| :-----------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------: |
| ![에러 조회](https://raw.githubusercontent.com/calmnature/pencraft/main/GIF/9.%EC%97%90%EB%9F%AC%20%EC%A1%B0%ED%9A%8C.gif) | ![Lot 조회](https://raw.githubusercontent.com/calmnature/pencraft/main/GIF/10.Lot%20%EC%A1%B0%ED%9A%8C.gif) |

<br><br><br><br>

<span id="7"></span>
## ⌨7. 핵심 코드
<details>
  <summary><b>1공정 ~ 4공정 생산 로직</b></summary>
  반복문을 이용하여 제품을 생산하면서 N초 주기로 웹 소켓을 통해 클라이언트에게 데이터를 보내야하기 때문에 2개의 Thread가 필요<br>
  쓰레드의 관리가 편리한 ExecutorService를 이용하여 2개의 쓰레드 풀을 만들어 '생산'과 '데이터 전송'을 동시에 진행
  <br><br>
  1공정 : 하나의 Lot에서 N개의 제품을 생성하기 때문에 Lot의 생성과 N개의 제품을 리스트에 담아 랜덤한 잉크를 주입하고 제품 규격과 비교하여 양품과 불량품을 리스트에 저장<br>
  1공정이 종료된 후 2공정 메서드 실행
  <br><br>
  2공정 : 1공정에서 생산된 제품 중 양품인 제품만 닙(보드마카의 촉)을 삽입을 하는데 랜덤하게 닙 깊이를 삽입하여 제품 규격과 비교하여 불량품일 경우 양품&불량품 여부의 값을 불량으로 변경<br>
  2공정이 종료된 후 3공정 메서드 실행
  <br><br>
  3공정 : 2공정에서 생산된 제품 중 양품인 제품만 몸체를 결합하는데 랜덤하게 결합 여부를 Y, N으로 하여 불량일 경우 양품&불량품 여부의 값을 불량으로 변경<br>
  3공정이 종료된 후 4공정 메서드 실행
  <br><br>
  4공정 : 3공정에서 생단된 제품 중 양품인 제품만 뚜껑을 결합하는데 3공정과 동일하게 랜덤으로하여 불량품일 경우 양품&불량품 여부의 값을 불량으로 변경<br>
  4공정이 종료된 후 생산된 제품과 Lot을 데이터 베이스에 저장하는 메서드 실행
  
```java
```

</details>

<br><br><br><br>

<span id="8"></span>
## 🚀8. 트러블 슈팅
<details>
  <summary><b>프론트 우선순위 에러</b></summary>
  <b>&gt; 현상</b><br>
  완성된 결과물에 웹을 꾸미는 과정에 페이지업하는 버튼의 정렬 불가 -> 인라인 스타일 시트로 강제 정렬
  
  ```java
  ```
  
</details>
<br><br><br><br>

<span id="9"></span>
## ⭕9. 리팩토링 완료
- **생산 공정 로직**
  - processStart() 메서드 실행 시 processTask() 메서드 호출
  - 각 공정 메서드인 processOne() ~ processFour() 실행
  - 각 공정 메서드는 각 공정마다 해야할 일들을 처리하고 각각 processOneLogic() ~ processFourLogic() 실행

- **일/월/년 데이터 로직**
  - 각각의 데이터가 '일일' '월별' '연별'로 달라지기 때문에 로그인 성공 후 메인 페이지 접속 시 LotService의 allDateSend() 호출
  - allDateSend()는 dayDateSend(), monthDateSend(), yearDateSend() 호출
  - 각각의 메서드는 findLot()를 호출하여 기준에 따라 DB에서 데이터를 가져와 저장
  - 클라이언트에게 보낼 데이터를 정제하기 위해 createMap() 메서드 호출
  - 기준에 따라 DateTimeFormatter.ofPattern()이 달라지고 Map에 데이터 저장
  - 각각의 데이터를 구독자 주소에 맞게 Send

- **JPA Repository Paging 기능**
  - 페이징은 0번부터 시작하므로 사용자가 요청한 페이지의 -1을 하여 조회 필요

- **Javascript 및 jQuery**
  - 메인페이지와 모니터링 페이지의 각 공정마다 그리는 그래프를 그리는 코드를 drawChart()라는 함수로 따로 관리
<br><br><br><br>

<span id="10"></span>
## ❗10. 보완 사항
- **비 로그인 시 권한이 없는 URL 접속할 경우 Alert창 추가**
  - **로그인이 되지 않은 상태**로 로그인 시 이용 가능한 주소창을 직접 입력할 경우 로그인 페이지로 필터가 되지만 특별한 알림창이 출력되지 않음
  - alert 창을 이용하여 '로그인이 필요합니다' 같은 알림창 추가
- **보안**
  - 현재 **로그인 성공 시 로그인 정보를 세션에 담기** 때문에 해당 세션을 가로챌 줄 아는 사람이라면 세션의 사용자의 아이디 비밀번호 등 개인 정보가 포함되어 있어 해당 부분 수정 필요
  - **회원 생성 시 사번과 비밀번호가 동일하게 설정**이 되어있는데, 사용자가 비밀번호를 변경하지 않을 시 누군가가 10001번부터 계속하여 입력하여 해당 아이디가 해킹되는 등의 보안을 어떻게 처리해야할 지 수정 필요
- **생산 중단 기능 확장**
  - **생산량 대비 불량률이 일정 수치가 넘어갈 경우** (2~4%) 기기 또는 어떠한 오류가 있을 것이라고 판단하여 **자동으로 생산을 중단**할 수 있는 기능 추가
  - 여러 개의 생산 지시를 내린 후 생산 중단 기능을 누를 경우 생산 지시가 모두 삭제 되어 **생산 중단 버튼 클릭 시 N개의 생산 지시 중 1개만 선택하여 해당 지시를 취소**할 수 있도록 로직 변경 필요
  - **N번 공정에서 생산 도중 생산 중단 버튼 클릭 시 모두 삭제,** 실무로 보면 3공정에서 중단 시 1~3공정까지 만들어진 모든 제품을 모두 버리고 1공정부터 새로 만들게 되는 식의 로직이기 때문에 생산 중단 시점에서 다시 시작할 수 있도록 로직 변경 필요
  - 생산 중단을 하였을 경우 어떤 사용자가 어떤 이유로 생산을 중단했는지 등의 로그나 확인 페이지 같은 것이 필요
- **페이징된 뷰 페이지(제품 조회, 에러 조회, Lot 조회) 검색 기능 추가**
  - 검색 기능 추가 및 세분화 및 정렬 기준 추가
<br><br><br><br>

<span id="11"></span>
## ☑11. 보완 완료
- **페이지 필터**
  - **로그인이 되지 않은 상태(세션에 로그인 정보가 없는 상태)에서 로그인 이외의 페이지를 요청을 할 경우 접근이 불가능**하고 로그인을 유도하기 위해 로그인 페이지로 이동
- **예외 처리**
  - Controller에 맵핑되지 않은 주소 요청이 올 경우 **Whitelabel Error Page가 아닌 만들어둔 400번, 500번 에러 페이지로 이동 가능**
- **생산 지시의 규격 추가**
  - 기존 로직으로는 1개의 규격으로만 생산을 하게 되어있었지만 **다른 규격이 추가되어 여러 개의 규격 중 선택**하여 생산 가능
- **모니터링 리팩토링**
  - 생산 지시 후 생산이 되고 있는 중에 다른 사용자가 모니터링 페이지에 접속하면 데이터를 정상적으로 수신할 수 있지만, 생산 중에만 데이터를 보내는 것이기 때문에 **생산 공정이 돌아가지 않을 때 모니터링 페이지 접속할 경우 가장 마지막의 데이터를 클라이언트에게 데이터를 전송**
- **비밀번호 변경**
  - 사용자가 본인이 사용하는 비밀번호대로 변경을 하기 위해 비밀번호 변경 기능 추가
- **로그인 시 빈 공백으로 로그인할 경우 에러페이지**
  - @Valid 어노테이션 바로 뒤에 BindingResult가 오도록 순서 변경하여 해결
- **생산 지시 후 동일한 데이터가 올 경우 중복 차트 그리지 않도록 수정**
  - 서버로부터 받은 데이터와 기존 차트의 데이터가 동일할 경우 그리지 않음
- **반응형 웹 페이지**
  - 모바일 환경에서 그래프가 제대로 출력되지 않아 부트스트랩 및 CSS를 활용하여 반응형 웹페이지 구성
- **Alert 변경**
  - 기본 alert이 너무 심플하여 CDN 추가 -> 좀 더 감각적인 디자인으로 Alert 수정
<br><br><br><br>

<span id="12"></span>
## 🙆‍♂️12. 느낀 점 및 아쉬운 점
