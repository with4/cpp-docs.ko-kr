---
title: "vi_progid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.vi_progid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vi_progid attribute"
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# vi_progid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

버전에 관계 없이 폼의 ProgID 지정합니다.  
  
## 구문  
  
```  
  
      [ vi_progid(  
   name  
) ];  
```  
  
#### 매개 변수  
 *name*  
 개체를 나타내는 버전 독립 ProgID입니다.  
  
 Progid는 사람이 읽을 수 있는 버전의 COM\/ActiveX 개체를 식별 하는 데 사용 되는 클래스 식별자 \(CLSID\)를 제공 합니다.  
  
## 설명  
 해당  **vi\_progid** C\+\+ 특성을 사용 하면 COM 개체에 대 한 버전 독립 Progid를 지정 합니다.  Progid를 폼 있습니다  *name1*.*name2*.*version*.  버전 독립적 Progid에 없는 한  *버전*.  둘 다를 지정할 수 있습니다의  **progid** 및  **vi\_progid** 의 coclass 특성을.  지정 하지 않으면  **vi\_progid**은 버전 종속 Progid가 지정 된 값입니다 있는  [progid](../windows/progid.md) 특성.  
  
 **vi\_progid** 의미 하는 것은  **coclass** 지정 하는 경우, 즉, 특성을  **vi\_progid**, 지정 하는 것 같은 것입니다 있는  **coclass** 및  **vi\_progid** 특성.  
  
 **Vi\_progid** 특성에서 지정한 이름이 자동으로 등록 하는 클래스를 발생 합니다.  생성 된.idl 파일 ProgID 값이 표시 됩니다.  
  
 ATL 프로젝트의 경우는  [coclass](../windows/coclass.md) 특성이 있다고도 하 고 지정 된 Progid를 사용 하 여는  **GetVersionIndependentProgID** 함수 \(삽입은  **coclass** 특성\).  
  
## 예제  
 참조는  [coclass](../windows/coclass.md) 샘플 사용을 예를 들어  **vi\_progid**.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**,`struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [ProgID Key](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)