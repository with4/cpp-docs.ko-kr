---
title: 재배포 가능 패키지 (c + +)를 사용 하 여 응용 프로그램 배포 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- walkthrough, deploying a Visual C++ application by using the redistributable package
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37bba00efdf0368973fa4ffbac1cbc6bb6298ce1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-the-visual-c-redistributable-package"></a>연습: Visual C++ 재배포 가능 패키지를 사용하여 Visual C++ 응용 프로그램 배포
이 문서에는 Visual c + + 재배포 가능 패키지를 사용 하 여 Visual c + + 응용 프로그램을 배포 하는 방법을 설명 합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료 하려면 이러한 구성 요소가 있어야 합니다.  
  
-   Visual Studio가 설치 되어 있는 컴퓨터입니다.  
  
-   Visual c + + 라이브러리를 하지 않은 추가 컴퓨터  
  
### <a name="to-use-the-visual-c-redistributable-package-to-deploy-an-application"></a>Visual c + + 재배포 가능 패키지를 사용 하 여 응용 프로그램을 배포 하려면  
  
1.  만들기 및 MFC 응용 프로그램에서 처음 3 단계를 수행 하 여 구축 [연습: 설치 프로젝트는 Visual c + + 응용 프로그램 사용 하 여 배포](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md)합니다.  
  
2.  파일을 만들고 setup.bat, 이름에 다음 명령을 추가 합니다. 변경 `MyMFCApplication` 프로젝트의 이름입니다.  
  
    ```cmd
    @echo off  
    vcredist_x86.exe  
    mkdir "C:\Program Files\MyMFCApplication"  
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"  
    ```  
  
3.  자동 압축 풀기 설치 파일을 만듭니다.  
  
    1.  또는 명령 프롬프트는 **실행** 창 iexpress.exe를 실행 합니다.  
  
    2.  선택 **새 자동 압축 풀기 지시문 파일 만들기** 선택한 후는 **다음** 단추입니다.  
  
    3.  선택 **파일 압축을 풀고 설치 명령 실행** 선택한 후 **다음**합니다.  
  
    4.  텍스트 상자에서 MFC 응용 프로그램의 이름을 입력 한 다음 **다음**합니다.  
  
    5.  에 **확인 메시지가** 페이지에서 **No 프롬프트** 선택한 후 **다음**합니다.  
  
    6.  에 **사용권 계약** 페이지에서 **라이선스를 표시 하지 않습니다** 선택한 후 **다음**합니다.  
  
    7.  에 **파일 패키지** 페이지, 다음 파일에 추가 하 고 다음 선택 **다음**합니다.  
  
        -   MFC 응용 프로그램 (.exe 파일)입니다.  
  
        -   vcredist_x86.exe 합니다. 이 파일은 \program files\microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\vcredist_x86 있습니다\\합니다.  
  
        -   이전 단계에서 만든 setup.bat 파일입니다.  
  
    8.  에 **설치 프로그램 시작을** 페이지는 **설치 프로그램** 텍스트 상자에서 다음 명령줄을 입력 한 다음 선택 **다음**합니다.  
  
         **cmd.exe /c "setup.bat"**  
  
    9. 에 **창 표시** 페이지에서 **기본** 선택한 후 **다음**합니다.  
  
    10. 에 **마침된 메시지** 페이지에서 **메시지가 없는** 선택한 후 **다음**합니다.  
  
    11. 에 **패키지 이름과 옵션** 페이지 자동 압축 풀기 설치 파일을 선택에 대 한 이름을 입력 합니다는 **패키지 내의 긴 파일 이름을 사용 하 여 파일을 저장할** 옵션을 선택한 후 **다음**. 파일 이름의 끝 MyMFCApplicationSetup.exe Setup.exe—for 등 이어야 합니다.  
  
    12. 에 **다시 시작 구성** 페이지에서 **다시 시작 하지** 선택한 후 **다음**합니다.  
  
    13. 에 **자동 압축 풀기 지시문 저장** 페이지에서 **저장 자동 압축 풀기 지시문 (SED) 파일** 선택한 후 **다음**합니다.  
  
    14. 에 **패키지 만들기** 페이지에서 선택 **다음**합니다.  
  
4.  Visual c + + 라이브러리에 없는 다른 컴퓨터에 자동 압축 풀기 설치 파일을 테스트 합니다.  
  
    1.  다른 컴퓨터에 설치 파일의 복사본을 다운로드 한 다음 실행 하 고 제공 하는 단계에서 설치 합니다.  
  
    2.  MFC 응용 프로그램을 실행 합니다.  
  
         설치 파일 자동 압축 풀기 2 단계에서 지정한 폴더에 있는 MFC 응용 프로그램을 설치 합니다. Visual c + + 재배포 가능 패키지 설치 관리자는 자동 압축 풀기 설치 파일에 포함 되어 있으므로 응용 프로그램을 성공적으로 실행 합니다.  
  
        > [!IMPORTANT]
        >  설치 된 런타임 버전을 확인 하려면 설치 관리자는 레지스트리 키 \HKLM\SOFTWARE\Microsoft\VisualStudio\11.0\VC\Runtimes 확인\\[플랫폼]. 현재 설치 된 버전에서 설치 관리자를 설치 하려는 버전 보다 최신인 경우 설치 관리자는 이전 버전을 설치 하지 않고 성공 했다는 결과가 반환 하 고 제어판에서 설치 된 프로그램 페이지에서 추가 항목을 상태로 둡니다.  
  
## <a name="see-also"></a>참고 항목  
 [배포 예제](../ide/deployment-examples.md)