---
title: "연습: Visual C++ 재배포 가능 패키지를 사용하여 Visual C++ 응용 프로그램 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "연습, 재배포 가능 패키지를 사용하여 Visual C++ 응용 프로그램 배포"
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연습: Visual C++ 재배포 가능 패키지를 사용하여 Visual C++ 응용 프로그램 배포
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 Visual C\+\+ 응용 프로그램을 배포 하려면 Visual C\+\+ 재배포 가능 패키지를 사용 하는 방법을 설명 합니다.  
  
## 사전 요구 사항  
 이 연습을 완료 하려면 다음 구성이 요소가 있어야 합니다.  
  
-   Visual Studio 설치 된 컴퓨터입니다.  
  
-   Visual C\+\+ 라이브러리가 없는 추가 컴퓨터  
  
### Visual C\+\+ 재배포 가능 패키지를 사용 하 여 응용 프로그램을 배포 하려면  
  
1.  처음 세 단계에 따라 MFC 응용 프로그램 빌드를 만들고 [Walkthrough: Deploying a Visual C\+\+ Application By Using a Setup Project](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
2.  파일을 만들 setup.bat를 이름과 다음 명령을 추가 하십시오.  변경 `MyMFCApplication` 프로젝트의 이름입니다.  
  
    ```  
    @echo off  
    vcredist_x86.exe  
    mkdir "C:\Program Files\MyMFCApplication"  
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"  
    ```  
  
3.  자동 압축 풀기 설치 파일을 만듭니다.  
  
    1.  명령 프롬프트에서 나는  **실행** iexpress.exe 실행 창에.  
  
    2.  선택  **새 자동 압축 풀기 지시문 파일 만들기** 다음 선택은  **다음** 단추.  
  
    3.  선택  **파일 압축 풀기 및 설치 명령 실행** 다음 선택  **다음**.  
  
    4.  MFC 응용 프로그램의 이름을 텍스트 상자에 입력 한 다음 선택  **다음**.  
  
    5.  에  **명령 프롬프트** 페이지에서  **아니요 프롬프트** 다음 선택  **다음**.  
  
    6.  에  **동의** 페이지에서  **라이센스를 표시 안 함** 다음 선택  **다음**.  
  
    7.  에  **패키지 된 파일** 페이지에서 다음 파일을 추가 하 고 다음 선택  **다음**.  
  
        -   MFC 응용 프로그램 \(.exe 파일\)입니다.  
  
        -   vcredist\_x86.exe.  이 파일은 SDKs\\Windows\\v7.0A\\Bootstrapper\\Packages\\vcredist\_x86\\ \\program files\\microsoft에 있습니다.  
  
        -   이전 단계에서 만든 setup.bat 파일입니다.  
  
    8.  에  **설치 프로그램을 실행** 페이지의  **설치 프로그램** 텍스트 상자에 다음 명령줄을 입력 한 다음 선택  **다음**.  
  
         **cmd.exe \/c "setup.bat"**  
  
    9. 에  **창 표시** 페이지에서  **기본** 다음 선택  **다음**.  
  
    10. 에  **완료 메시지** 페이지에서  **메시지** 다음 선택  **다음**.  
  
    11. 에  **패키지 이름 및 옵션** 페이지에서 자동 압축 풀기 설치 파일을 선택에 대 한 이름을 입력은  **패키지 내의 긴 파일 이름을 사용 하 여 저장소 파일** 옵션을 선택한 다음 선택  **다음**.  파일 이름 끝에 Setup.exe—for 예를 들어, MyMFCApplicationSetup.exe 이어야 합니다.  
  
    12. 에  **구성 다시** 페이지에서  **다시** 다음 선택  **다음**.  
  
    13. 에  **자동 압축 풀기 지시문 저장** 페이지에서  **저장 자동 압축 풀기 지시어 \(SED\) 파일** 다음 선택  **다음**.  
  
    14. 에  **만들기 패키지** 페이지에서 선택  **다음**.  
  
4.  자동 압축 풀기 설치 파일 Visual C\+\+ 라이브러리가 없는 때 다른 컴퓨터를 테스트 합니다.  
  
    1.  다른 컴퓨터에서 설치 프로그램 파일의 복사본을 다운로드 하 고 실행 하 고 제공 단계를 수행 하 여 설치 합니다.  
  
    2.  MFC 응용 프로그램 실행  
  
         자동 압축 풀기 설치 파일은 2단계에서 지정한 폴더에 MFC 응용 프로그램을 설치합니다.  Visual C\+\+ 재배포 가능 패키지 설치 관리자가 자동 압축 풀기 설치 파일에 포함되어 있기 때문에 이 응용 프로그램은 성공적으로 실행됩니다.  
  
        > [!IMPORTANT]
        >  설치 된 런타임 버전을 확인 하려면 설치 관리자가 레지스트리 키 \\HKLM\\SOFTWARE\\Microsoft\\VisualStudio\\11.0\\VC\\Runtimes\\\[platform 확인\] 합니다.  현재 설치 된 버전 설치 프로그램을 설치 하려고 버전 보다 더 최신 이면 설치 관리자가 이전 버전을 설치 하지 않고 성공을 반환 하 고 제어판에서 설치 된 프로그램 페이지 추가 항목을 둡니다.  
  
## 참고 항목  
 [배포 예제](../ide/deployment-examples.md)