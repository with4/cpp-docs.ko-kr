---
title: "방법: Windows 데스크톱 응용 프로그램에서 Windows 10 SDK 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# 방법: Windows 데스크톱 응용 프로그램에서 Windows 10 SDK 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)]에서 클래식 Windows 데스크톱 프로젝트를 만들면 이 프로젝트는 Windows 8.1 SDK를 사용하여 빌드되도록 기본적으로 설정됩니다. 이 버전의 Windows SDK는 Windows 10 등의 모든 최근 Windows 릴리스와 호환되지만 최신 Windows 10 API 및 Windows 10 SDK에 있는 CRT 함수는 포함되지 않습니다. 새로운 API를 사용하려는 경우에는 프로젝트가 Windows 10 SDK를 참조하도록 대상을 다시 지정할 수 있습니다.  
  
 [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] 및 Windows 10 SDK부터는 CRT 라이브러리가 유니버설 Windows 앱에서 사용할 수 있는 함수가 포함된 부분\(ucrtbase\)과 다른 모든 항목이 포함된 부분\(vcruntime140\)의 두 부분으로 분리되었습니다. Windows 10 SDK 이후로는 다수의 C99 함수와 같은 새로운 함수가 있으며, 이러한 함수를 사용하려면 다음 단계를 따라야 합니다.[CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)을 참조하세요.  
  
### Windows 10 SDK를 대상으로 하려면  
  
1.  Windows 10 SDK가 설치되었는지 확인합니다. Windows 10 SDK는 [Windows 10용 도구](http://go.microsoft.com/fwlink/?LinkID=617631)의 일부로 설치됩니다.  
  
2.  프로젝트 노드에 대한 바로 가기 메뉴를 열고 **SDK 버전 대상 다시 지정**을 선택합니다.  
  
     ![SDK 버전 대상 다시 지정](../windows/media/retargetingwindowssdk1.png "RetargetingWindowsSDK1")  
  
     **솔루션 작업 검토** 대화 상자가 나타납니다.  
  
     ![솔루션 작업 검토](../windows/media/retargetingwindowssdk2.png "RetargetingWindowsSDK2")  
  
3.  **대상 플랫폼 버전** 드롭다운 목록에서 대상으로 하려는 Windows 10 SDK의 버전을 선택하거나 변경하지 않으려면 8.1을 선택합니다. 확인 단추를 선택하여 변경 내용을 적용합니다.  
  
     이 컨텍스트에서 8.1이란 Windows SDK를 말하며 이는 또는 Windows 8, Windows Server 2012, Windows 7, Windows Server 2008 및 Windows Vista와 이전 버전 호환성을 가집니다.  
  
     이 단계에 성공한 경우 출력 창에 다음 텍스트가 나타납니다.  
  
     `대상 변경 종료: 1개 완료, 0개 실패, 0개 건너뜀`  
  
4.  프로젝트 속성을 열고 **구성 속성, 일반** 섹션에서 **Windows 대상 플랫폼 버전**의 값을 확인합니다. 여기서 이 값을 변경하면 이 절차를 따르는 것과 효과가 같습니다.[일반 속성 페이지\(프로젝트\)](../ide/general-property-page-project.md)을 참조하세요.  
  
     ![대상 플랫폼 버전](../windows/media/retargetingwindowssdk3.png "RetargetingWindowsSDK3")  
  
     이 작업은 헤더 파일 및 라이브러리 파일에 대한 경로가 포함된 프로젝트 매크로의 값을 변경합니다. 변경 내용을 확인하려면 프로젝트 속성 대화 상자의 Visual C\+\+ 디렉터리 섹션에서 포함 디렉터리와 같이 속성 중 하나를 선택하고 드롭다운 목록을 선택해서 연 다음 \<편집\>을 선택합니다.**포함 디렉터리** 대화 상자가 나타납니다.  
  
     ![포함 디렉터리 대화 상자](../windows/media/retargetingwindowssdk4.png "RetargetingWindowsSDK4")  
  
     **매크로 \>\>**단추를 선택하고 매크로 목록을 Windows SDK 매크로까지 아래로 스크롤하여 모든 새 값을 표시합니다.  
  
     ![Windows SDK 매크로](../windows/media/retargetingwindowssdk5.png "RetargetingWindowsSDK5")  
  
5.  필요에 따라 다른 프로젝트에 대해 이 작업을 반복하고 솔루션을 다시 빌드합니다.  
  
### Windows 8.1 SDK를 대상으로 하려면  
  
1.  프로젝트 노드에 대한 바로 가기 메뉴를 열고 **SDK 버전 대상 다시 지정**을 선택합니다.  
  
2.  대상 플랫폼 버전 드롭다운 목록에서 8.1을 선택합니다.  
  
## 참고 항목  
 [Windows Desktop Applications \(Visual C\+\+\)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)