---
title: retval | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.retval
dev_langs: C++
helpviewer_keywords: retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf7aa0cf8dd9767f603807ee18e23fe02d3446c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="retval"></a>retval
멤버의 반환 값을 받는 매개 변수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[retval]  
  
```  
  
## <a name="remarks"></a>설명  
 **retval** c + + 특성에 동일한 기능을는 [retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) MIDL 특성입니다.  
  
 **retval** 마지막 인수는 함수 선언에서에 표시 되어야 합니다.  
  
## <a name="example"></a>예  
 예를 참조 [바인딩 가능한](../windows/bindable.md) 의 샘플 사용에 대 한 **retval**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 매개 변수를 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|**out**|  
|**잘못된 특성**|**in**|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [매개 변수 특성](../windows/parameter-attributes.md)   
 [메서드 특성](../windows/method-attributes.md)   
