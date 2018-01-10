---
title: "날짜 및 시간: SYSTEMTIME 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: SYSTEMTIME
dev_langs: C++
helpviewer_keywords:
- system time
- FILETIME structure, with CTime class
- time [C++], formatting
- SYSTEMTIME structure
- dates [C++], MFC
- formatting [C++], time
ms.assetid: 201528e4-2ffa-48fc-af8f-203aa86d942a
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 405c245cdab6426330915c945cd77f8336e68c9d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="date-and-time-systemtime-support"></a>날짜 및 시간: SYSTEMTIME 지원
[CTime](../atl-mfc-shared/reference/ctime-class.md) 클래스에 Win32에서 시스템 및 파일 시간을 허용 하는 생성자입니다. 이러한 용도로 `CTime` 개체를 사용하는 경우 이 문서에서 설명하는 대로 해당 초기화를 적절하게 수정해야 합니다.  
  
 SYSTEMTIME 구조체에 대 한 정보를 참조 하십시오. [SYSTEMTIME](../mfc/reference/systemtime-structure1.md)합니다. FILETIME 구조체에 대 한 정보를 참조 하십시오. [FILETIME](../mfc/reference/filetime-structure.md)합니다.  
  
 MFC는 MS-DOS 스타일의 시간 인수를 가져오는 `CTime` 생성자를 계속 제공합니다. 그러나 MFC 버전 3.0부터 `CTime` 클래스는 Win32 `SYSTEMTIME` 구조체를 가져오는 생성자와 Win32 `FILETIME` 구조체를 가져오는 또 다른 생성자도 지원합니다.  
  
 새로운 `CTime` 생성자는 다음과 같습니다.  
  
-   CTime (const SYSTEMTIME & `sysTime`);  
  
-   CTime (const FILETIME & `fileTime`);  
  
 `fileTime` 매개 변수는 Win32 `FILETIME` 구조체에 대한 참조이며 시간을 64비트 값으로 나타냅니다. 이는 `SYSTEMTIME` 구조체에 비해 내부 저장용으로 편리한 형식이자 파일 만들기 시간을 나타내기 위해 Win32에서 사용하는 시간입니다.  
  
 시스템 시간을 사용하여 초기화된 `CTime` 개체가 코드에 있으면 Win32에서 `SYSTEMTIME` 생성자를 사용해야 합니다.  
  
 경우는 거의 사용 하지 것입니다 `CTime` `FILETIME` 직접 초기화 합니다. 사용 하는 경우는 `CFile` 파일을 조작 하는 개체 [CFile::GetStatus](../mfc/reference/cfile-class.md#getstatus) 를 통해 파일 타임 스탬프를 검색 한 `CTime` 사용 하 여 개체 초기화는 `FILETIME` 구조입니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [일반적인 날짜 및 시간 프로그래밍 MFC의](../atl-mfc-shared/date-and-time.md)  
  
-   [날짜 및 시간 프로그래밍 자동 지원](../atl-mfc-shared/date-and-time-automation-support.md)  
  
-   [날짜 및 시간 프로그래밍을 위한 범용 클래스](../atl-mfc-shared/date-and-time-general-purpose-classes.md)  
  
## <a name="see-also"></a>참고 항목  
 [날짜 및 시간](../atl-mfc-shared/date-and-time.md)

