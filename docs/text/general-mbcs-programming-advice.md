---
title: "일반적인 MBCS 프로그래밍 팁 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "대화 상자[C++], 글꼴"
  - "MBCS[C++], 대화 상자 글꼴"
  - "MBCS[C++], 프로그래밍"
  - "MS Shell Dlg"
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
caps.latest.revision: 9
caps.handback.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# 일반적인 MBCS 프로그래밍 팁
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 팁을 사용하십시오.  
  
-   유연성을 위해 가능하면 런타임 매크로\(예: `_tcschr` 및 `_tcscpy`\)를 사용합니다.  자세한 내용은 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)을 참조하십시오.  
  
-   C 런타임 `_getmbcp` 함수를 사용하여 현재 코드 페이지에 대한 정보를 가져옵니다.  
  
-   문자열 리소스를 다시 사용하지 않습니다.  대상 언어에 따라 지정된 문자열은 변환할 때 의미가 달라질 수 있습니다.  예를 들어, 응용 프로그램의 주 메뉴에 있는 "파일"은 대화 상자의 "파일" 문자열과 다르게 번역될 수 있습니다.  같은 이름의 문자열을 여러 개 사용해야 할 경우 각 문자열에 대해 다른 문자열 ID를 사용하십시오.  
  
-   응용 프로그램이 MBCS를 사용할 수 있는 운영 체제에서 실행되고 있는지를 확인할 수 있습니다.  그렇게 하려면 프로그램을 시작할 때 플래그를 설정합니다. API 호출에 의존하지 마십시오.  
  
-   대화 상자를 설계할 때 정적 텍스트 컨트롤의 끝에 MBCS 변환을 위해 30% 정도의 여유 공간을 확보합니다.  
  
-   일부 시스템에서 사용할 수 없는 글꼴이 있기 때문에 응용 프로그램의 글꼴을 선택할 때 주의합니다.  예를 들어, Windows 2000 일본어 버전은 Helvetica 글꼴을 지원하지 않습니다.  
  
-   대화 상자의 글꼴을 선택할 때 MS Sans Serif나 Helvetica 대신 [MS Shell Dlg](http://msdn.microsoft.com/library/windows/desktop/dd374112)를 선택합니다.  MS Shell Dlg는 대화 상자를 만들기 전에 시스템에 의해 올바른 글꼴로 대체됩니다.  MS Shell Dlg를 사용하면 이 글꼴을 처리하기 위해 운영 체제에서 변경한 내용이 자동으로 제공됩니다. MFC는 MS Shell Dlg를 DEFAULT\_GUI\_FONT나 Windows 95, Windows 98 및 Windows NT 4의 시스템 글꼴로 변경합니다. 이들 시스템에서는 MS Shell Dlg를 올바르게 처리하지 못합니다.  
  
-   응용 프로그램을 설계할 때 지역화할 수 있는 문자열과 지역화할 수 없는 문자열을 결정합니다.  잘 모르겠으면 지정된 모든 문자열이 지역화된다고 가정합니다.  이와 같이 지역화할 수 있는 문자열을 지역화할 수 없는 문자열과 함께 사용하지 마십시오.  
  
## 참고 항목  
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)   
 [포인터 증가 및 감소](../text/incrementing-and-decrementing-pointers.md)