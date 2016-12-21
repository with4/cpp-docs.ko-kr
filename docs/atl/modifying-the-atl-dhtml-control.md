---
title: "Modifying the ATL DHTML Control | Microsoft Docs"
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
  - "DHTML controls"
  - "DHTML controls, 수정"
  - "HTML 컨트롤, 수정"
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Modifying the ATL DHTML Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL 컨트롤 마법사 빌드 및 컨트롤을 실행할 수 있도록 하 고 어떻게 메서드는 프로젝트 파일에 쓰고 DHTML이 디스패치 메서드를 사용 하 여 컨트롤의 C\+\+ 코드를 호출 하는 방법을 볼 수 있도록 기초 코드를 제공 합니다.  디스패치 메서드를 인터페이스에 추가할 수 있습니다.  그런 다음 HTML 리소스에서 메서드를 호출할 수 있습니다.  
  
#### ATL DHTML 컨트롤을 수정 하려면  
  
1.  클래스 뷰에서 컨트롤 프로젝트를 확장 합니다.  
  
     "UI"로 끝나는 인터페이스 메서드 하나가 있는지 참고 `OnClick`.  "UI" 끝나지 않은 인터페이스 메서드가 없습니다.  
  
2.  호출 하는 메서드를 추가 합니다. `MethodInvoked` "UI"에서 끝나지 않는 인터페이스  
  
     이 방법에 DHTML에서 사용 되는 컨트롤과 상호 작용 하는 인터페이스가 아닌 컨테이너 상호 작용 컨트롤 컨테이너에 사용 되는 인터페이스에 추가 됩니다.  컨테이너 에서만이 메서드를 호출할 수 있습니다.  
  
3.  .Cpp 파일에서 스텁 해제 된 메서드를 찾아 예를 들어 메시지 상자를 표시 하는 코드를 추가:  
  
     [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/CPP/modifying-the-atl-dhtml-control_1.cpp)]  
  
4.  호출 하는 다른 메서드를 추가 합니다. `HelloHTML`,이 시간에만 끝나는 "UI"에 인터페이스 추가 스텁 해제 된 아웃 찾기 `HelloHTML` 메서드는.cpp에서 파일 하 고 예를 들어 메시지 상자를 표시 하는 코드를 추가:  
  
     [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/CPP/modifying-the-atl-dhtml-control_2.cpp)]  
  
5.  세 번째 방법은, 추가 `GoToURL`, "UI"에서 끝나지 않는 인터페이스 이 메서드를 호출 하 여 구현  [IWebBrowser2::Navigate](https://msdn.microsoft.com/en-us/library/aa752133.aspx), 다음과 같이 하십시오.  
  
     [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/CPP/modifying-the-atl-dhtml-control_3.cpp)]  
  
     사용할 수 있는  **IWebBrowser2** 메서드.h 파일에 ATL에 대 한 인터페이스 포인터를 제공 하기 때문에.  
  
 그런 다음 만든 메서드를 호출 하 여 HTML 리소스를 수정 합니다.  이러한 메서드를 호출 하는 세 개의 단추를 추가 합니다.  
  
#### HTML 리소스 수정  
  
1.  솔루션 탐색기에서 HTML 리소스를 표시 하려면.htm 파일을 두 번 누릅니다.  
  
     특히 외부 Windows 디스패치 메서드를 호출 하는 HTML을 검토 합니다.  프로젝트의 HTML 호출 `OnClick` 메서드 및 매개 변수를 나타내는 컨트롤의 본문 \(`theBody`\) 및 색 지정 \("`red`"\).  메서드 호출 다음에 오는 텍스트 단추에 표시 되는 레이블입니다.  
  
2.  다른 추가 `OnClick` 메서드는 색만 변경 합니다.  예를 들면 다음과 같습니다.  
  
    ```  
    <br>  
    <br>  
    <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>  
    ```  
  
     이 메서드는 단추를 만듭니다  **새로**, 사용자 컨트롤 원본, 흰색 배경으로 반환 합니다 수 있습니다.  
  
3.  호출을 추가 하는 `HelloHTML` 메서드를 작성 합니다.  예를 들면 다음과 같습니다.  
  
    ```  
    <br>  
    <br>  
    <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>  
    ```  
  
     이 메서드는 단추를 만듭니다  **HelloHTML**를 표시 하려면 사용자가 클릭할 수 있는 `HelloHTML` 메시지 상자.  
  
 이제 빌드 수 및  [수정 된 DHTML 컨트롤 테스트](../atl/testing-the-modified-atl-dhtml-control.md).  
  
## 참고 항목  
 [DHTML 컨트롤에 대한 지원](../atl/atl-support-for-dhtml-controls.md)