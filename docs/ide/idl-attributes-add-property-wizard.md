---
title: "속성 추가 마법사, IDL 특성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.prop.idlattributes"
dev_langs: 
  - "C++"
ms.assetid: 356ed666-79d0-4bd9-a5e7-cda679cbadbd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 속성 추가 마법사, IDL 특성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

속성 추가 마법사의 이 페이지에서 속성에 IDL\(인터페이스 정의 언어\) 설정을 지정할 수 있습니다.  
  
 **id**  
 속성을 나타내는 숫자 ID를 설정합니다.  사용자 지정 인터페이스의 속성에는 이 옵션을 사용할 수 없습니다.  *MIDL Reference*에서 [id](http://msdn.microsoft.com/library/windows/desktop/aa367040)를 참조하십시오.  
  
 **HelpContext**  
 사용자가 도움말 파일에서 이 속성에 대한 정보를 볼 수 있도록 해주는 컨텍스트 ID를 지정합니다.   MIDL Reference에서 [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851)를 참조하십시오.  
  
 **helpstring**  
 문자열이 적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.  기본적으로 "property *속성이름*"으로 설정됩니다. *MIDL Reference*에서 [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856)을 참조하십시오.  
  
## 다른 옵션  
 속성 형식마다 사용할 수 있는 옵션이 다릅니다.  
  
|옵션|설명|  
|--------|--------|  
|**bindable**|속성이 데이터 바인딩을 지원합니다.  *MIDL Reference*에서 [bindable](http://msdn.microsoft.com/library/windows/desktop/aa366738)을 참조하십시오.  속성의 스톡 구현에서는 기본적으로 이 옵션이 설정되며 변경될 수 없습니다.|  
|**defaultbind**|이 하나의 바인딩할 수 있는 속성이 개체를 가장 잘 나타냅니다.  *MIDL Reference*에서 [defaultbind](http://msdn.microsoft.com/library/windows/desktop/aa366790)를 참조하십시오.|  
|**displaybind**|이 속성은 사용자에게 bindable로 표시되어야 합니다.  *MIDL Reference*에서 [displaybind](http://msdn.microsoft.com/library/windows/desktop/aa366804)를 참조하십시오.|  
|**immediatebind**|데이터 바인딩된 개체의 이 속성에 대한 모든 변경 내용이 즉시 데이터베이스에 통보됩니다.  *MIDL Reference*에서 [immediatebind](http://msdn.microsoft.com/library/windows/desktop/aa367045)를 참조하십시오.|  
|**defaultcollelem**|속성이 기본 컬렉션의 요소에 대한 접근자 함수입니다.  *MIDL Reference*에서 [defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792)을 참조하십시오.|  
|**nonbrowsable**|속성 브라우저에 표시되지 않아야 할 인터페이스나 dispinterface 멤버에 태그를 붙입니다.  *MIDL Reference*에서 [nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117)을 참조하십시오.|  
|**requestedit**|속성이 **OnRequestEdit** 알림을 지원합니다. *MIDL Reference*에서 [requestedit](http://msdn.microsoft.com/library/windows/desktop/aa367155)를 참조하십시오.  속성의 스톡 구현에서는 기본적으로 이 옵션이 설정되며 변경될 수 없습니다.|  
|**source**|속성의 멤버가 이벤트의 소스입니다.  *MIDL Reference*에서 [source](http://msdn.microsoft.com/library/windows/desktop/aa367166)를 참조하십시오.|  
|**hidden**|속성이 있지만 사용자 기반 브라우저에는 표시되지 않아야 합니다.  *MIDL Reference*에서 [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861)을 참조하십시오.|  
|**restricted**|속성을 임의로 호출할 수 없습니다.  *MIDL Reference*에서 [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157)를 참조하십시오.|  
|`local`|원격 속성이 아님을 MIDL 컴파일러에 지정합니다.  *MIDL Reference*에서 [local](http://msdn.microsoft.com/library/windows/desktop/aa367071)을 참조하십시오.|  
  
## 참고 항목  
 [속성 추가](../ide/adding-a-property-visual-cpp.md)   
 [속성 추가 마법사, 이름](../ide/names-add-property-wizard.md)   
 [인터페이스 구현](../ide/implementing-an-interface-visual-cpp.md)   
 [스톡 속성](../ide/stock-properties.md)