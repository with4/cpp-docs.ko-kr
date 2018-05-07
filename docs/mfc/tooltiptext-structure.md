---
title: TOOLTIPTEXT 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TOOLTIPTEXT
dev_langs:
- C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f64a93529905e84fe043947772e55b9332b5106e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="tooltiptext-structure"></a>TOOLTIPTEXT 구조체
쓰기에서는 프로그램 [도구 설명 알림 처리기](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)를 사용 해야는 `TOOLTIPTEXT` 구조입니다. 멤버는 `TOOLTIPTEXT` 구조:  
  
 `typedef struct {`  
  
 `NMHDR     hdr;        // required for all WM_NOTIFY messages`  
  
 `LPTSTR    lpszText;   // see below`  
  
 `TCHAR     szText[80]; // buffer for tool tip text`  
  
 `HINSTANCE hinst;      // see below`  
  
 `UINT      uflags;     // flag indicating how to interpret the`  
  
 `// idFrom member of the NMHDR structure`  
  
 `// that is included in the structure`  
  
 `} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;`  
  
 `hdr`  
 텍스트를 필요한 도구를 식별 합니다. 이 구조 해야의 유일한 구성원은 컨트롤의 명령 id입니다. 컨트롤의 명령 ID에 포함 됩니다는 `idFrom` 의 멤버는 `NMHDR` 구문을 사용 하 여 액세스할 구조 `hdr.idFrom`합니다. 참조 [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) 의 멤버에 대 한 내용은 `NMHDR` 구조입니다.  
  
 `lpszText`  
 도구에 대 한 텍스트를 수신 하는 문자열의 주소입니다.  
  
 `szText`  
 도구 설명 텍스트를 받는 버퍼입니다. 응용 프로그램 문자열 주소를 지정 하는 대신이 버퍼에 텍스트를 복사할 수 있습니다.  
  
 `hinst`  
 도구 설명 텍스트로 사용할 문자열을 포함 하는 인스턴스 핸들입니다. 경우 `lpszText` 주소 도구 설명 텍스트의이 멤버는 NULL입니다.  
  
 처리 하는 `TTN_NEEDTEXT` 알림 메시지를 다음 방법 중 하나에 표시할 문자열을 지정 합니다.  
  
-   텍스트 복사로 지정 된 버퍼는 `szText` 멤버입니다.  
  
-   텍스트를 포함 하는 버퍼의 주소를 복사는 `lpszText` 멤버입니다.  
  
-   문자열 리소스의 식별자를 복사는 `lpszText` 멤버 및 리소스를 포함 하는 인스턴스 핸들 복사는 `hinst` 멤버입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CFrameWnd에서 파생되지 않은 창의 도구 설명](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

