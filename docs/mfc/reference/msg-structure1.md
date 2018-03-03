---
title: "메시지 구조 1 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MSG
dev_langs:
- C++
helpviewer_keywords:
- MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b504f116dcbff7fa45e741ff9715070ee0c74583
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="msg-structure1"></a>메시지 구조 1
`MSG` 구조는 스레드의 메시지 큐에서 메시지 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagMSG {     // msg    
    HWND hwnd;  
    UINT message;  
    WPARAM wParam;  
    LPARAM lParam;  
    DWORD time;  
    POINT pt;  
} MSG;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *hwnd*  
 창 메시지를 수신 하는 창 프로시저를 식별 합니다.  
  
 `message`  
 메시지 번호를 지정합니다.  
  
 `wParam`  
 메시지에 대 한 추가 정보를 지정 합니다. 값에 따라 정확한 의미는 **메시지** 멤버입니다.  
  
 `lParam`  
 메시지에 대 한 추가 정보를 지정 합니다. 값에 따라 정확한 의미는 **메시지** 멤버입니다.  
  
 `time`  
 메시지가 게시 된 시간을 지정 합니다.  
  
 `pt`  
 메시지 게시 될 때 커서 위치 화면 좌표를 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winuser.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

