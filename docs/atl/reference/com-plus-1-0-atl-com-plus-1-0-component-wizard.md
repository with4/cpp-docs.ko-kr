---
title: "COM + 1.0, ATL COM + 1.0 구성 요소 마법사 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.mts.options
dev_langs:
- C++
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 36295e5ce296ea6ba982c4ce8cf729bf45860883
ms.lasthandoff: 02/24/2017

---
# <a name="com-10-atl-com-10-component-wizard"></a>COM+ 1.0, ATL COM+ 1.0 구성 요소 마법사
ATL 구성 된 COM + 1.0 구성 요소 마법사의이 페이지를 사용 하 여 지원 해야 하는 인터페이스 형식 및 인터페이스를 추가로 지정할 수 있습니다.  
  
 ATL 프로젝트와 ATL COM 클래스에 대 한 자세한 내용은 참조 하십시오. [ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)합니다.  
  
 **인터페이스**  
 개체가 지 원하는 인터페이스의 형식을 나타냅니다. 개체는 기본적으로 이중 인터페이스를 지원합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**이중**|개체는 이중 인터페이스 지원 하도록 지정 (해당 vtable에 인터페이스를 사용자 지정 함수 및 런타임에 바인딩 `IDispatch` 메서드). COM 클라이언트와 자동화 컨트롤러에서 개체에 액세스할 수 있습니다.|  
|**사용자 지정**|개체는 사용자 지정 인터페이스 (사용자 지정 인터페이스 함수)를 지원 하는지 지정 합니다. 프로세스 경계를 넘어 특히 사용자 지정 인터페이스는 이중 인터페이스 보다 빠를 수 있습니다.<br /><br /> -   **자동화 호환** 자동화 지원을 사용자 지정 인터페이스에 추가 합니다. 특성 사용된 프로젝트에 대 한 설정의 **oleautomation** coclass의 특성입니다.|  
  
 **큐 사용 가능**  
 클라이언트에서 비동기적으로 메시지 큐를 사용 하 여이 구성 요소를 호출할 수 있음을 나타냅니다. .Idl 파일 (프로젝트의 하지 않는 경우) 또는.h 파일 (특성 사용된 하는 프로젝트)에 특성을 사용 하는 구성 요소 매크로 사용자 지정 (TLBATTR_QUEUEABLE, 0)를 추가합니다.  
  
 **지원**  
 오류 처리 및 개체 컨트롤에 대 한 추가 지원을 나타냅니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**ISupportErrorInfo**|에 대 한 지원을 만듭니다는 [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) 인터페이스 개체를 클라이언트에 오류 정보를 반환할 수 있도록 합니다.|  
|**IObjectControl**|세 가지에 대 한 개체 액세스를 제공 [IObjectControl](http://msdn.microsoft.com/library/windows/desktop/ms686474) 메서드: [활성화](http://msdn.microsoft.com/library/windows/desktop/ms681303), [CanBePooled](http://msdn.microsoft.com/library/windows/desktop/ms684322), 및 [비활성화](http://msdn.microsoft.com/library/windows/desktop/ms687094)합니다.|  
|**IObjectConstruct**|에 대 한 지원을 만듭니다는 [IObjectConstruct](http://msdn.microsoft.com/library/windows/desktop/ms680583) 다른 방법이 나 개체의 매개 변수에서 전달 관리 하는 인터페이스입니다.|  
  
 **트랜잭션**  
 개체가 트랜잭션을 지원 하는지 나타냅니다. 파일 mtxattr.h.idl 파일 (하지 않는 프로젝트)를 포함합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**지원**|개체 루트가 되지 트랜잭션 스트림의.idl 파일 (하지 않는 프로젝트) 구성 요소 특성 매크로 custom(TLBATTR_TRANS_SUPPORTED,0).h 파일 (특성 사용된 하는 프로젝트)에 추가 하 여 지정 합니다.|  
|**필수**|사용자 지정 하는 개체 되거나.idl 파일 (하지 않는 프로젝트) 구성 요소 특성 매크로 custom(TLBATTR_TRANS_REQUIRED,0).h 파일 (특성 사용된 하는 프로젝트)에 추가 하 여 트랜잭션 스트림의 루트 되지 않을 수 있습니다.|  
|**지원 되지 않음**|개체가 트랜잭션을 제외를 지정 합니다. .H 파일 (특성 사용된 프로젝트) 또는.idl 파일 (하지 않는 프로젝트) 매크로 tlbattr_trans_notsupp,&0; 구성 요소 특성을 추가합니다.|  
|**새 트랜잭션 필요**|하는 개체는 항상 루트 트랜잭션 스트림의.h 파일 (특성 사용된 프로젝트) 또는.idl 파일 (하지 않는 프로젝트) 매크로 tlbattr_trans_reqnew,&0; 구성 요소 특성을 추가 하 여 지정 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [ATL COM + 1.0 구성 요소 마법사](../../atl/reference/atl-com-plus-1-0-component-wizard.md)   
 [ATL COM + 1.0 구성 요소](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)


