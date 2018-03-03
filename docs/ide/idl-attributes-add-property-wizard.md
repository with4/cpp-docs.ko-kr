---
title: "추가 속성 마법사, IDL 특성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.prop.idlattributes
dev_langs:
- C++
ms.assetid: 356ed666-79d0-4bd9-a5e7-cda679cbadbd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ec158c117161c5a5c2ffd23cef0d5c79c312ae7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="idl-attributes-add-property-wizard"></a>속성 추가 마법사, IDL 특성
속성 추가 마법사의이 페이지를 사용 하 여 속성에 대 한 인터페이스 정의 (IDL) 언어 설정을 지정 합니다.  
  
 **ID**  
 속성을 식별 하는 숫자 ID를 설정 합니다. 이 옵션은 사용자 지정 인터페이스의 속성에 사용할 수 없습니다. 참조 [id](http://msdn.microsoft.com/library/windows/desktop/aa367040) 에 *MIDL 참조*합니다.  
  
 **helpcontext**  
 사용자는 도움말 파일에서이 속성에 대 한 정보를 볼 수 있는 컨텍스트 ID를 지정 합니다. 참조 [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) 에 *MIDL 참조*합니다.  
  
 **helpstring**  
 적용 되는 요소에 설명 하는 데 사용 되는 문자열을 지정 합니다. 기본적으로 설정은 "속성 *속성 이름*." 참조 [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) 에 *MIDL 참조*합니다.  
  
## <a name="other-options"></a>기타 옵션  
 일부 옵션은 모든 속성 유형에 사용할 수 있습니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**bindable**|속성이 데이터 바인딩을 지원 하는지 나타냅니다. 참조 [바인딩 가능한](http://msdn.microsoft.com/library/windows/desktop/aa366738) 에 *MIDL 참조*합니다. 속성 스톡 구현에 대 한이 옵션은 기본적으로 설정 하 고은 변경할 수 없습니다.|  
|**defaultbind**|나타낸다는 것을 의미이 최상의 바인딩할 수 있는 단일 속성 개체입니다. 참조 [defaultbind](http://msdn.microsoft.com/library/windows/desktop/aa366790) 에 *MIDL 참조*합니다.|  
|**displaybind**|이 속성으로 바인딩할 수 있는 사용자에 게 표시할지 나타냅니다. 참조 [displaybind](http://msdn.microsoft.com/library/windows/desktop/aa366804) 에 *MIDL 참조*합니다.|  
|**immediatebind**|데이터 바인딩된 개체의이 속성에 대 한 모든 변경의 데이터베이스를 즉시 된다는 있는지를 나타냅니다. 참조 [immediatebind](http://msdn.microsoft.com/library/windows/desktop/aa367045) 에 *MIDL 참조*합니다.|  
|**defaultcollelem**|속성은 기본 컬렉션의 요소에 대 한 접근자 함수 임을 나타냅니다. 참조 [defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792) 에 *MIDL 참조*합니다.|  
|**nonbrowsable**|속성 브라우저에 표시 될 인터페이스 또는 dispinterface 멤버를 태그를 삽입 합니다. 참조 [nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117) 에 *MIDL 참조*합니다.|  
|**requestedit**|속성을 지원 하는지 나타냅니다는 **OnRequestEdit** 알림 참조 [requestedit](http://msdn.microsoft.com/library/windows/desktop/aa367155) 에 *MIDL 참조*합니다. 속성 스톡 구현에 대 한이 옵션은 기본적으로 설정 하 고은 변경할 수 없습니다.|  
|**소스**|이벤트의 소스 속성의 멤버 임을 나타냅니다. 참조 [소스](http://msdn.microsoft.com/library/windows/desktop/aa367166) 에 *MIDL 참조*합니다.|  
|**hidden**|속성이 있지만 하지 사용자 기반 브라우저에 표시할지 나타냅니다. 참조 [숨겨진](http://msdn.microsoft.com/library/windows/desktop/aa366861) 에 *MIDL 참조*합니다.|  
|**restricted**|속성 임의로 호출할 수 없도록 지정 합니다. 참조 [제한](http://msdn.microsoft.com/library/windows/desktop/aa367157) 에 *MIDL 참조*합니다.|  
|`local`|원격 속성이 아님을 MIDL 컴파일러에 지정 합니다. 참조 [로컬](http://msdn.microsoft.com/library/windows/desktop/aa367071) 에 *MIDL 참조*합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [속성 추가](../ide/adding-a-property-visual-cpp.md)   
 [이름, 속성 추가 마법사](../ide/names-add-property-wizard.md)   
 [인터페이스 구현](../ide/implementing-an-interface-visual-cpp.md)   
 [스톡 속성](../ide/stock-properties.md)