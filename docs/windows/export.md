---
title: "내보내기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.export
dev_langs: C++
helpviewer_keywords: export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 24619e3a0e707b40590b0ffb37b415629a18b1cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="export"></a>내보내기
데이터 구조는.idl 파일에 배치 하면 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[export]  
  
```  
  
## <a name="remarks"></a>설명  
 **내보내기** c + + 특성을 사용 하면.idl 파일에 배치 하 고 다음에서 사용 하려면 모든 언어와 함께 사용 하기 위해 사용할 수 있도록 하는 이진 호환 형식으로 형식 라이브러리는 데이터 구조입니다.  
  
 적용할 수 없습니다는 **내보내기** 특성을 클래스에는 클래스에 공용 멤버를만 경우에 (해당 하는 한 `struct`).  
  
 명명 되지 않은 내보내면 `enum`s 또는 `struct`s로 시작 하는 지정 된 이름을 수 **__unnamed***x*여기서 *x* 은 일련 번호입니다.  
  
 내보내기에 대 한 유효한 형식 정의 기본 형식, 구조체, 공용 구조체, 열거형, 하거나 식별자를 입력 합니다.  참조 [typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예  
 다음 코드에서는 사용 하 여 **내보내기** 특성:  
  
```  
// cpp_attr_ref_export.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**union**, `typedef`, `enum`, `struct`, 또는`interface`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 특성](../windows/compiler-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
