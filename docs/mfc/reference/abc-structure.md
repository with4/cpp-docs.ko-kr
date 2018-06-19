---
title: ABC 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ABC
dev_langs:
- C++
helpviewer_keywords:
- ABC structure [MFC]
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61b5f67247b556b37cdf934f94c30947675533e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346492"
---
# <a name="abc-structure"></a>ABC 구조체
**ABC** 구조 트루타입 글꼴이에 문자 너비를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _ABC { /* abc */  
    int abcA;  
    UINT abcB;  
    int abcC;  
} ABC;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *abcA*  
 문자 A 간격을 지정 합니다. A 간격은 거리 문자 모양이 그리기 전에 현재 위치를 추가 합니다.  
  
 *abcB*  
 문자의 B 간격을 지정 합니다. B 간격은 문자 모양이 그려지는 부분의 너비입니다.  
  
 *abcC*  
 문자의 C 간격을 지정 합니다. C 간격은 문자 모양이의 오른쪽에 흰색 공간 제공 하기 위해 현재 위치에 추가할 거리를 설정 합니다.  
  
## <a name="remarks"></a>설명  
 전체 너비의 문자는 A, B 및 C 공간의 합계입니다. C 간격이 나 A underhangs 또는 돌출부 나타내기 위해 음수일 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


