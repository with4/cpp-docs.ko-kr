---
title: ON_UPDATE_COMMAND_UI 매크로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_UPDATE_COMMAND_UI
dev_langs:
- C++
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- update handlers [MFC]
- command-handler macros
- updating user-interface objects [MFC]
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 726eba2edbb857784a3a23ddcfb2d69fd8e30a72
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="onupdatecommandui-macro"></a>ON_UPDATE_COMMAND_UI 매크로
사용 하 여는 **속성** 명령 대상 개체에서 명령 업데이트 처리기에는 사용자 인터페이스 개체를 연결 하는 창입니다. 사용자 인터페이스 개체의 ID를 자동으로 연결 된 `ON_UPDATE_COMMAND_UI` 매크로 및 업데이트를 처리 하는 개체에 핸들을 만듭니다. 참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md) 자세한 정보에 대 한 합니다.  
  
 예를 들어 프로그램의 편집 메뉴에서 모두 지우기 명령을 업데이트 하려면 사용는 **속성** 명령 업데이트 처리기에 대 한 함수 선언 선택한 클래스의 메시지 맵 항목을 추가 하는 창이 `OnUpdateEditClearAll` 클래스 선언과 클래스의 구현 파일에 있는 빈 함수 템플릿. 함수 프로토타입에 다음과 같습니다.  
  
 [!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]  
  
 함수에 표시 된 모든 처리기와 같은 **afx_msg** 키워드입니다. 하나의 인수 즉에 대 한 포인터 걸리는 모든 업데이트 처리기와 같은 한 `CCmdUI` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 사용자 인터페이스 개체 업데이트](../mfc/how-to-update-user-interface-objects.md)

