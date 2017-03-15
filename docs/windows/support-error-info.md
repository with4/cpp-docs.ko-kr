---
title: "support_error_info | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.support_error_info"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "support_error_info 특성"
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# support_error_info
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

자세한 오류 반환에 대한 지원을 구현합니다.  
  
## 구문  
  
```  
  
[ support_error_info(  
   error_interface=  
uuid  
) ]  
  
```  
  
#### 매개 변수  
 **error\_interface**  
 **IErrorInfo**를 구현하는 인터페이스의 식별자입니다.  
  
## 설명  
 **support\_error\_info** C\+\+ 특성은 대상 개체에서 발생한 자세한 상황별 오류를 클라이언트에 반환하는 작업에 대한 지원을 구현합니다. 오류를 지원하려면 개체는 **IErrorInfo** 인터페이스의 메서드를 구현해야 합니다. 자세한 내용은 [IDispatch 및 IErrorInfo 지원](../atl/supporting-idispatch-and-ierrorinfo.md)을 참조하세요.  
  
 이 특성은 [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) 클래스를 대상 개체에 기본 클래스로 추가합니다. 이는 **ISupportErrorInfo**의 기본 구현으로 이어지며, 단일 인터페이스가 개체에서 오류를 일으킬 때 사용할 수 있습니다.  
  
## 예제  
 다음 코드는 **ISupportErrorInfo** 인터페이스에 대한 기본 지원을 `CMyClass` 개체에 추가합니다.  
  
```  
// cpp_attr_ref_support_error_info.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="mymod")];  
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]  
__interface IMyErrors  
{  
};  
  
[ coclass, support_error_info("IMyErrors"),  
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]  
class CMyClass  
{  
};  
```  
  
## 요구 사항  
  
### 특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**|  
|**반복 가능**|예|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## 참고 항목  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)