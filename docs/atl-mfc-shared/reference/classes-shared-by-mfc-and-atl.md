---
title: "MFC와 ATL에서 공유 되는 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "공유 클래스"
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# MFC와 ATL에서 공유 되는 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 표에서 MFC와 ATL. 사이 공유 클래스를 보여 줍니다.  
  
|클래스|설명|헤더 파일|  
|-----------|-----------------|-----------------|  
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|파일과 관련 된 날짜 및 시간 값을 관리 하기 위한 메서드를 제공 합니다.|atltime.h|  
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|상대 날짜 및 시간 값에 연결 된 파일을 관리 하기 위한 메서드를 제공 합니다.|atltime.h|  
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|문자열 개체가 고정된 문자 버퍼를 나타냅니다.|cstringt.h|  
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|로드 하 고 이미지를 JPEG, GIF, BMP, 및 PNG 이동식 네트워크 그래픽 () 형식으로 저장 하는 기능 등의 향상 된 비트맵 지원을 제공 합니다.|atlimage.h|  
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|캡슐화 된 **날짜** OLE 자동화에 사용 된 데이터 형식입니다.|atlcomtime.h|  
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|상대 시간을 시간 범위를 나타냅니다.|atlcomtime.h|  
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|Windows와 유사한 클래스 [지점](../../mfc/reference/point-structure1.md) 조작 하는 멤버 함수를 포함 하는 구조 `CPoint` 및 **지점** 구조입니다.|atltypes.h|  
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|Windows와 유사한 클래스 [RECT](../../mfc/reference/rect-structure1.md) 조작 하는 멤버 함수를 포함 하는 구조 `CRect` 개체 및 Windows `RECT` 구조입니다.|atltypes.h|  
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|나타냅니다는 `CSimpleStringT` 개체입니다.|atlsimpstr.h|  
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|클래스는 상대 좌표 또는 위치를 구현 하는 창 크기 구조와 유사 합니다.|atltypes.h|  
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|자동 리소스 정리에 대 한 제공 `GetBuffer` 및 `ReleaseBuffer` 호출 하는 기존 `CStringT` 개체입니다.|atlsimpstr.h|  
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|String 개체의 데이터를 나타냅니다.|atlsimpstr.h|  
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|나타냅니다는 `CStringT` 개체입니다.|cstringt.h (MFC 따라 다름) atlstr.h (MFC 독립적)|  
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|절대 시간 및 날짜를 나타냅니다.|atltime.h|  
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|내부적으로 시간 범위에서 수 시간 (초)으로 저장 되는 시간 만큼 합니다.|atltime.h|  
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|인터페이스를 나타내는 `CStringT` 메모리 관리자입니다.|atlsimpstr.h|  
  
## <a name="see-also"></a>참고 항목  
 [ATL/MFC 클래스 공유](../../atl-mfc-shared/atl-mfc-shared-classes.md)


