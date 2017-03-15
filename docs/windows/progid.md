---
title: "progid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.progid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "progid attribute"
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# progid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM 개체에 대 한 Progid를 지정합니다.  
  
## 구문  
  
```  
  
      [ progid(  
   name  
) ];  
```  
  
#### 매개 변수  
 *name*  
 개체가 나타내는 ProgID입니다.  
  
 Progid는 사람이 읽을 수 있는 버전의 COM\/ActiveX 개체를 식별 하는 데 사용 되는 클래스 식별자 \(CLSID\)를 제공 합니다.  
  
## 설명  
 해당  **progid** C\+\+ 특성을 사용 하면 COM 개체에 대 한 Progid를 지정 합니다.  Progid를 폼 있습니다  *name1*.*name2*.*version*.  지정 하지 않은 경우는  *버전* Progid에 대 한 기본 버전은 1입니다.  지정 하지 않으면  *name1*. *name2*, 기본 이름인  *클래스 이름*. *클래스 이름*.  지정 하지 않으면  **progid** 지정 하지  **vi\_progid**,  *name1*. *name2* 에서 가져옵니다  **vi\_progid** 하 여 \(다음 일련 번호\) 버전이 추가 됩니다.  
  
 특성 블록을 사용 하는 경우  **progid** 도 사용 하지 않는 `uuid`, 컴파일러 레지스트리 있는지 여부를 확인 한 `uuid` 존재에 대 한 지정 된  **progid**.  경우  **progid** 지정 하지 않으면 버전 \(및 coclass를 만드는 경우 coclass 이름\) 사용 됩니다를 생성할 수 있는  **progid**.  
  
 **progid** 의미 하는 것은  **coclass** 지정 하는 경우, 즉, 특성을  **progid**, 지정 하는 것 같은 것입니다 있는  **coclass** 및  **progid** 특성.  
  
 **Progid** 특성에서 지정한 이름이 자동으로 등록 하는 클래스를 발생 합니다.  생성 된.idl 파일은 표시 되지 것입니다을  **progid** 값입니다.  
  
 ATL을 사용 하는 프로젝트 내에서이 특성을 사용 하는 경우 특성의 동작을 변경 합니다.  위의 문제 이외에이 특성으로 지정 된 정보에 사용 되는  **GetProgID** 으로 삽입 된 함수는  **coclass** 특성.  자세한 내용은 참조 하십시오 있는  [coclass](../windows/coclass.md) 특성.  
  
## 예제  
 예제를 보려면  [coclass](../windows/coclass.md) 의 샘플 사용에 대 한  **progid**.  
  
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
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [ProgID Key](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)