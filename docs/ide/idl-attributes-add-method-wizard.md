---
title: "메서드 추가 마법사, IDL 특성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.method.idlattrib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메서드 추가 마법사[C++]"
  - "IDL 특성, 메서드 추가 마법사"
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 메서드 추가 마법사, IDL 특성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

메서드 추가 마법사의 이 페이지에서는 메서드에 IDL\(인터페이스 정의 언어\) 설정을 지정할 수 있습니다.  
  
 **id**  
 메서드를 나타내는 숫자 ID를 설정합니다.  *MIDL Reference*에서 [id](http://msdn.microsoft.com/library/windows/desktop/aa367040)를 참조하십시오.  
  
 이 상자는 사용자 지정 인터페이스와 MFC dispinterface에 사용할 수 없습니다.  
  
 **call\_as**  
 이 로컬 메서드를 매핑할 수 있는 원격 메서드의 이름을 지정합니다.  *MIDL Reference*에서 [call\_as](http://msdn.microsoft.com/library/windows/desktop/aa366748)를 참조하십시오.  
  
 MFC dispinterface에는 사용할 수 없습니다.  
  
 **HelpContext**  
 사용자가 도움말 파일에서 이 메서드에 대한 정보를 볼 수 있도록 해주는 컨텍스트 ID를 지정합니다.  MIDL Reference에서 [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851)를 참조하십시오.  
  
 MFC dispinterface에는 사용할 수 없습니다.  
  
 **helpstring**  
 문자열이 적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.  기본적으로 "method 메서드 이름"으로 설정됩니다. *MIDL Reference*에서 [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856)을 참조하십시오.  
  
 MFC dispinterface에는 사용할 수 없습니다.  
  
 **추가 특성**  
 MFC dispinterface에는 사용할 수 없습니다.  
  
|특성|설명|  
|--------|--------|  
|**hidden**|메서드가 존재하지만 사용자 기반 브라우저에는 표시되지 않습니다.  *MIDL Reference*에서 [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861)을 참조하십시오.|  
|**source**|메서드의 멤버가 이벤트의 소스입니다.  *MIDL Reference*에서 [source](http://msdn.microsoft.com/library/windows/desktop/aa367166)를 참조하십시오.|  
|`local`|원격 메서드가 아님을 MIDL 컴파일러에 지정합니다.  *MIDL Reference*에서 [local](http://msdn.microsoft.com/library/windows/desktop/aa367071)을 참조하십시오.|  
|**restricted**|메서드를 임의로 호출할 수 없습니다.  *MIDL Reference*에서 [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157)를 참조하십시오.|  
|**vararg**|메서드에서 다양한 개수의 인수를 사용합니다.  다양한 개수의 인수를 사용하려면 마지막 인수가 남아 있는 모든 인수를 포함하는 **VARIANT** 형식의 안전 배열이어야 합니다.  *MIDL Reference*에서 [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304)를 참조하십시오.|  
  
## 참고 항목  
 [메서드 추가](../ide/adding-a-method-visual-cpp.md)   
 [메서드 추가 마법사](../ide/add-method-wizard.md)