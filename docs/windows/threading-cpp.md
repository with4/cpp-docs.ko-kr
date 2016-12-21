---
title: "threading (C++) | Microsoft Docs"
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
  - "vc-attr.threading"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "threading attribute"
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# threading (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM 개체의 스레딩 모델을 지정합니다.  
  
## 구문  
  
```  
  
      [ threading(  
   model=enumeration  
) ]  
```  
  
#### 매개 변수  
 ***모델*** \(옵션\)  
 다음과 같은 스레딩 모델 중 하나:  
  
-   **아파트** \(아파트 스레딩\)  
  
-   **중립** \(.NET Framework 구성 요소와 사용자 인터페이스는 없습니다\)  
  
-   **단일** \(단순 스레딩\)  
  
-   **사용할 수 있는** \(자유 스레딩\)  
  
-   **둘 다** \(아파트 및 자유 스레딩을\)  
  
 기본값은  **아파트**.  
  
## 설명  
 해당  **스레딩** C\+\+ 특성은 생성 된.idl 파일에 표시 되지만 COM 개체의 구현에서 사용 됩니다.  
  
 ATL 프로젝트의 경우는  [coclass](../windows/coclass.md) 특성이 수도 있는 경우 스레딩 모델이 지정 된  *모델* 템플릿 매개 변수로 전달 되는  [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) 클래스를 삽입는  **coclass** 특성.  
  
 **스레딩** 특성에도 액세스할 수 보호 된  [event\_source](../windows/event-source.md).  
  
## 예제  
 참조는  [사용이 허가 된](../windows/licensed.md) 샘플 사용을 예를 들어  **스레딩**.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**,`struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|**coclass**|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [COM Attributes](../windows/com-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [이전 코드를 위한 다중 스레드 지원\(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [Neutral Apartments](http://msdn.microsoft.com/library/windows/desktop/ms681813)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)