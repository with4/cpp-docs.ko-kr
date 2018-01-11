---
title: no_injected_text | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.no_injected_text
dev_langs: C++
helpviewer_keywords: no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c74d3134b5381be4ec330742726b26fea6155da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="noinjectedtext"></a>no_injected_text
특성 사용 결과로 코드 주입에서 컴파일러를 방지 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ no_injected_text(  
   boolean  
) ];  
```  
  
#### <a name="parameters"></a>매개 변수  
 `boolean`(선택 사항)  
 **true 이면** 없는 코드를 삽입, **false** 코드를 삽입할 수 있도록 합니다. **true** 값이 기본값입니다.  
  
## <a name="remarks"></a>설명  
 가장 일반적인 용도 **no_injected_text** 하 여 c + + 특성은는 [/Fx](../build/reference/fx-merge-injected-code.md) 삽입 컴파일러 옵션을는 **no_injected_text** .mrg 파일에는 특성입니다.  
  
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
 [컴파일러 특성](../windows/compiler-attributes.md)   
