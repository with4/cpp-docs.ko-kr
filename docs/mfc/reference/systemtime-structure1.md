---
title: "SYSTEMTIME 구조&1; | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- SYSTEMTIME structure
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 298b2673a3eb05525683f8269fcd415d5be1c80a
ms.lasthandoff: 02/24/2017

---
# <a name="systemtime-structure1"></a>SYSTEMTIME 구조&1;
`SYSTEMTIME` 구조체는 날짜 및 월, 일, 연도, 요일, 시간, 분, 초 및 밀리초에 대 한 개별 멤버를 사용 하 여 시간을 나타냅니다.  
  
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
 현재 월입니다. 1 월은 1입니다.  
  
 *wDayOfWeek*  
 현재 요일을; 일요일은 0, 월요일은 1, 합니다.  
  
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
 [!code-cpp[NVC_MFC_Utilities #&39;](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winbase.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)


