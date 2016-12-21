---
title: "idl_quote | Microsoft Docs"
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
  - "vc-attr.idl_quote"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "idl_quote attribute"
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# idl_quote
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

생성 된.idl 파일을 통해 전달할 수 및 Visual C\+\+의 현재 버전에서 지원 되지 않는 IDL 구문을 사용할 수 있습니다.  
  
## 구문  
  
```  
  
      [ idl_quote(  
   text  
) ]  
```  
  
#### 매개 변수  
 *text*  
 Visual C\+\+ 컴파일러에서 컴파일러 오류를 반환 하지 않고를 통해 생성 된.idl 파일을 전달 하는 특성 이름입니다.  
  
## 설명  
 경우는  **idl\_quote** C\+\+ 특성으로 사용 됩니다 \(세미콜론 닫는 대괄호 뒤에\)를 사용 하 여 독립 실행형 특성 다음  *텍스트*  으로 병합 된.idl 파일에 저장 됩니다.  경우  **idl\_quote** 는 심볼을 사용  *텍스트*  해당 기호에 대 한 특성 블록 내에 배치 됩니다.  
  
## 예제  
 다음 코드에 지원 되지 않는 특성을 지정 하는 수 있습니다 보여 줍니다 \(를 사용 하 여  **에서**, 지원 되\) 정의 및 정의 되지 않은.idl 구문을 사용 하는 방법:  
  
```  
// cpp_attr_ref_idl_quote.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLibrary")];  
  
[export]  
struct MYFLOT {  
   int i;  
};  
  
[export]  
struct MYDUB {  
   int i;  
};  
  
[idl_quote("typedef union _S1_TYPE switch (long l1) U1_TYPE { case 1024: \  
struct MYFLOT f1; case 2048: struct MYDUB d2; } S1_TYPE;") ];  
  
typedef struct _S1_TYPE {   
   long l1;   
  
union {   
   MYFLOT f1; MYDUB d2; } U1_TYPE;   
} S1_TYPE;  
  
[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), object]  
__interface IStatic{  
   HRESULT Func1([idl_quote("in")] int i);  
   HRESULT func( S1_TYPE* myStruct );  
};  
```  
  
 MYFLOT 및 MYDUB이이 코드에서 발생 하는  *텍스트* 항목에서 생성 된.idl 파일을 추가할 수 있습니다.  *이름* 매개 변수가 힘  *텍스트* 를 참조 하는 것 보다 먼저 배치할 수  *이름* 생성 된.idl 파일에.  *종속성* 매개 변수 종속성 목록 정의 앞에 배치 됩니다  *텍스트* 생성 된.idl 파일에 있습니다.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치에|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)