---
title: "개체 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.object
dev_langs: C++
helpviewer_keywords: object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5714d7c3bd029c7b1df636044ed1968f53600848
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="object-c"></a>object(C++)
사용자 지정 인터페이스를 식별합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[object]  
  
```  
  
## <a name="remarks"></a>설명  
 인터페이스 정의 앞에 오는 경우는 **개체** c + + 특성을 사용 하면 사용자 지정 인터페이스는.idl 파일에 배치 하는 인터페이스입니다.  
  
 개체와 함께 표시 된 모든 인터페이스에서 상속 해야 **IUnknown**합니다. 모든 기본 인터페이스에서 상속 하는 경우이 조건이 만족 **IUnknown**합니다. 상속 된 기본 인터페이스가 없는 경우 **IUnknown**, 컴파일러로 표시 된 인터페이스 하면 **개체** 를 파생할 **IUnknown**합니다.  
  
## <a name="example"></a>예  
 참조 [nonbrowsable](../windows/nonbrowsable.md) 사용 하는 방법의 예 **개체**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|`interface`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [인터페이스 특성](../windows/interface-attributes.md)   
 [이중](../windows/dual.md)   
 [dispinterface](../windows/dispinterface.md)   
 [사용자 지정](../windows/custom-cpp.md)   
 [__interface](../cpp/interface.md)   
