---
title: PAINTSTRUCT 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- PAINTSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75a3db6c6beb18afe2303b464fcab290b2e132fc
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338212"
---
# <a name="paintstruct-structure"></a>PAINTSTRUCT 구조체
`PAINTSTRUCT` 구조 창의 클라이언트 영역을 그리는 데 사용할 수 있는 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagPAINTSTRUCT {  
    HDC hdc;  
    BOOL fErase;  
    RECT rcPaint;  
    BOOL fRestore;  
    BOOL fIncUpdate;  
    BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *hdc*  
 그리기에 사용 되는 디스플레이 컨텍스트를 식별 합니다.  
  
 *fErase*  
 배경을 그려야 해야 하는지 여부를 지정 합니다. 없는 응용 프로그램 배경을 그리면 0입니다. 응용 프로그램은 배경 브러시를 하지 않고 Windows 창을-클래스를 만들 경우 배경을 그리기 위한 (에 대 한 설명을 참조를 `hbrBackground` 의 멤버는 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Windows SDK의 구조).  
  
 *rcPaint*  
 왼쪽 위를 지정 하 고 그리기 요청은 사각형의 오른쪽 모퉁이 절감 합니다.  
  
 *fRestore*  
 예약 된 멤버입니다. Windows에서 내부적으로 사용 됩니다.  
  
 *fIncUpdate*  
 예약 된 멤버입니다. Windows에서 내부적으로 사용 됩니다.  
  
 *rgbReserved [16]*  
 예약 된 멤버입니다. 예약 된 메모리 블록을 Windows에서 내부적으로 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winuser.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)

