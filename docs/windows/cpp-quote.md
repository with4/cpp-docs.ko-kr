---
title: cpp_quote | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.cpp_quote
dev_langs:
- C++
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 95b43856401b5bccfa9a0bef12fdc93ec886cea1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cppquote"></a>cpp_quote
생성 된.idl 파일에 인용 문자 없이 지정된 된 문자열을 내보냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ cpp_quote(  
   "statement"  
) ];  
```  
  
#### <a name="parameters"></a>매개 변수  
 *statement*  
 C 명령입니다.  
  
## <a name="remarks"></a>설명  
 **cpp_quote** c + + 특성은.idl 파일에서 전처리기 지시문을 삽입 하려는 경우에 유용 합니다.  
  
 사용할 수도 있습니다 **cpp_quote** MIDL 컴파일의 일부로.h 파일을 생성 합니다. 예를 들어 c + + IDL 특성을 사용 하지만 일부 작업에 대 한이 파일을 사용할 수 없습니다는 c + + 헤더 파일을 만든 경우 다음 컴파일할 수 있습니다 사용할 수 있어야 하 고 있으므로 MIDL 생성.h 파일을 만드는 것입니다.  
  
 **cpp_quote** 특성와 동일한 기능에는 [cpp_quote](http://msdn.microsoft.com/library/windows/desktop/aa366765) MIDL 특성입니다.  
  
## <a name="example"></a>예  
 예를 참조 [이중](../windows/dual.md) 예제를 보려면 사용 하는 방법을 사용 하 여 **cpp_quote**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [독립 실행형 특성](../windows/stand-alone-attributes.md)   
