---
title: "CCmdUI 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CCmdUI
dev_langs: C++
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: efb87fc04ee9ee55806ec4fc1103ded42231b433
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="the-ccmdui-class"></a>CCmdUI 클래스
프레임 워크를 update 명령 처리기를 라우팅하여 때 처리기에 대 한 포인터를 전달 된 `CCmdUI` 개체 (또는 개체에 `CCmdUI`-파생 클래스). 이 개체는 메뉴 항목이 나 도구 모음 단추 또는 해당 명령을 생성 하는 다른 사용자 인터페이스 개체를 나타냅니다. 업데이트 처리기는 멤버의 함수를 호출는 `CCmdUI` 사용자 인터페이스 개체 업데이트에 대 한 포인터를 통해 구조입니다. 예를 들어 다음은 모두 지우기 메뉴 항목에 대 한 업데이트 처리기가입니다.  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]  
  
 호출 하는이 처리기는 **사용** 메뉴 항목에 액세스할 수 있는 개체의 멤버 함수입니다. **사용 하도록 설정** 사용 하기 위해 사용할 수 있는 항목을 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 사용자 인터페이스 개체 업데이트](../mfc/how-to-update-user-interface-objects.md)

