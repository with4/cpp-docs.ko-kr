---
title: "문서에서 명령 처리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8d27698d573e1dee539f93ab88015285648fa77
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="handling-commands-in-the-document"></a>문서에서 명령 처리
문서 클래스에는 메뉴 항목, 도구 모음 단추 또는 액셀러레이터 키에 의해 생성 되는 특정 명령을 처리할 수도 있습니다. 기본적으로 **CDocument** 저장을 처리 하 고 serialization을 사용 하 여 파일 메뉴에 있는 명령을 다른 이름으로 저장 합니다. 데이터에 영향을 주는 다른 명령은 문서 멤버 함수에 의해 처리할 수도 있습니다. 예를 들어 Scribble 프로그램에서 클래스 `CScribDoc` 현재 문서에 저장 된 데이터를 모두 삭제 편집 모두 지우기 명령에 대 한 처리기를 제공 합니다. 문서에는 메시지 맵 있을 수 있지만 문서 보기와 달리 표준 Windows 메시지를 처리할 수 없습니다-만 **WM_COMMAND** 메시지 또는 "명령입니다."  
  
## <a name="see-also"></a>참고 항목  
 [문서 사용](../mfc/using-documents.md)

