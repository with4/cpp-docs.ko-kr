---
title: "uuid (C++ Attributes) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.uuid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uuid attribute"
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# uuid (C++ Attributes)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스 또는 인터페이스에 대 한 고유 ID를 지정합니다.  
  
## 구문  
  
```  
  
      [ uuid(  
   "uuid"  
) ]  
```  
  
#### 매개 변수  
 *uuid*  
 128 비트의 고유한 식별자입니다.  
  
## 설명  
 인터페이스 또는 클래스의 정의 지정 하지 않은 경우는 `uuid` C\+\+ 특성 다음 Visual C\+\+ 컴파일러는 제공 하나.  지정 된 `uuid`, 인용 부호를 포함 해야 합니다.  
  
 지정 하지 않으면 `uuid`, 컴파일러의 컴퓨터에서 서로 다른 특성 프로젝트 이름이 같은 클래스 또는 인터페이스의 GUID를 생성 합니다.  
  
 Uuidgen.exe 또는 guidgen.exe를 자신의 고유 Id를 생성 수 있습니다.  \(이러한 도구 중 하나를 실행 하십시오  **시작** 를 클릭 하 고  **실행** 메뉴입니다.  다음 필수 도구의 이름을 입력 하십시오.\)  
  
 ATL을 사용 하지 않는 프로젝트에서 사용 하는 경우를 지정 하는 `uuid` 특성입니다 지정 하는 것과  [uuid](../cpp/uuid-cpp.md) \_\_declspec 한정자입니다.  검색 하는 `uuid` 클래스를 사용 하면 수 있습니다  [\_\_uuidof](../cpp/uuidof-operator.md)  
  
## 예제  
 참조는  [바인딩할 수 있는](../windows/bindable.md) 샘플 사용을 예를 들어 `uuid`.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**class**, `struct`, `interface`, **union**,`enum`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [uuid](http://msdn.microsoft.com/library/windows/desktop/aa367302)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)