---
title: 내보내기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.export
dev_langs:
- C++
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 48c4a645456e3b3c0556dfed268ce911e5799fc3
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569419"
---
# <a name="export"></a>내보내기
.Idl 파일에 배치할 데이터 구조를 하면 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
[export]  
```  
  
## <a name="remarks"></a>설명  
 합니다 **내보내기** c + + 특성을 사용 하면 다음에서 사용 하려면 모든 언어를 사용할 수 있도록 하는 이진 호환 형식으로 형식 라이브러리 및.idl 파일에 배치할 데이터 구조입니다.  
  
 적용할 수 없습니다는 **내보내기** 클래스에는 공용 멤버가 포함 하는 경우에 클래스에 특성 (해당 하는 **구조체**).  
  
 명명 되지 않은 내보내면 **열거형**s 또는 **구조체**시작 하는 지정 된 이름 수를 **__unnamed * * * x*여기서 *x* 는 순차적 수입니다.  
  
 Typedef 내보내기에 대 한 유효한 기본 형식, 구조체, 공용 구조체, 열거형 또는 형식 식별자.  참조 [typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287) 자세한 내용은 합니다.  
  
## <a name="example"></a>예  
 다음 코드에서는 사용 하 여 **내보내기** 특성:  
  
```cpp  
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
|**적용 대상**|**union**, **typedef**를 **enum**를 **구조체**, 또는 **인터페이스**|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 특성](../windows/compiler-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   