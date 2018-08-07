---
title: SYSTEMTIME 구조 1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97a0042adaa223fc5898c057f191f7b750fa230f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372394"
---
# <a name="systemtime-structure1"></a>SYSTEMTIME 구조 1
`SYSTEMTIME` 구조는 날짜 및 시간을 월, 일, 연도, 요일, 시, 분, 초 및 밀리초에 대 한 개별 멤버를 사용 하 여 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _SYSTEMTIME {  
    WORD wYear;  
    WORD wMonth;  
    WORD wDayOfWeek;  
    WORD wDay;  
    WORD wHour;  
    WORD wMinute;  
    WORD wSecond;  
    WORD wMilliseconds;  
} SYSTEMTIME;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *wYear*  
 현재 연도입니다.  
  
 *wMonth*  
 현재 달; 1 월은 1입니다.  
  
 *wDayOfWeek*  
 주;의 현재 날짜 일요일은 0, 월요일은 1, 합니다.  
  
 *wDay*  
 해당 월의 현재 날짜입니다.  
  
 *wHour*  
 현재 시간입니다.  
  
 *wMinute*  
 현재 분입니다.  
  
 *wSecond*  
 현재 초입니다.  
  
 *wMilliseconds*  
 현재 밀리초입니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winbase.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

