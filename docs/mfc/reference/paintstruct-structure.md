---
title: "PAINTSTRUCT 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PAINTSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92583bba3dca60caa2895966a87571dc60805475
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
 그리기에 사용할 디스플레이 컨텍스트를 식별 합니다.  
  
 *fErase*  
 배경을 그릴 해야 하는지 여부를 지정 합니다. 없는 백그라운드 응용 프로그램을 다시 그릴 경우에 0입니다. 응용 프로그램은 배경 브러시 없이 Windows 창 클래스를 만들면 배경을 그리기에 대 한 (의 설명을 참조는 **hbrBackground** 의 멤버는 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) 구조 windows SDK).  
  
 *rcPaint*  
 왼쪽 위에 지정, 그리기 요청 된 사각형의 오른쪽 모퉁이입니다.  
  
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

