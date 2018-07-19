---
title: 사용자 정의 처리기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.handlers
dev_langs:
- C++
helpviewer_keywords:
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_MESSAGE macro [MFC]
- user-defined handlers [MFC]
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fdc8c70f7ef9bdd04bf40f408c4e014b3e3faa3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373248"
---
# <a name="user-defined-handlers"></a>사용자 정의 처리기
다음 맵 항목 함수 프로토타입을에 해당합니다.  
  
|맵 항목|함수 프로토타입|  
|---------------|------------------------|  
|ON_MESSAGE ( \<메시지 >, \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM, LPARAM);|  
|ON_REGISTERED_MESSAGE ( \<nMessageVariable >, \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM, LPARAM);|  
|ON_THREAD_MESSAGE ( \<메시지 >, \<memberFxn >)|afx_msg void memberFxn (WPARAM, LPARAM);|  
|ON_REGISTERED_THREAD_MESSAGE ( \<nMessageVariable >, \<memberFxn >)|afx_msg void memberFxn (WPARAM, LPARAM);|  
  
## <a name="see-also"></a>참고 항목  
 [메시지 맵](../../mfc/reference/message-maps-mfc.md)   
 [WM_ 메시지 처리기](../../mfc/reference/handlers-for-wm-messages.md)

