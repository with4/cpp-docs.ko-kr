---
title: "C 언어 API 관계 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.mfc
dev_langs: C++
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 26458242ab6afcf69d6e70065ba70e31f0adbe74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="relationship-to-the-c-language-api"></a>C 언어 API와의 관계
다른 클래스 라이브러리 외에도 Windows 용 Microsoft Foundation 클래스 (MFC) 라이브러리를 설정 하는 단일 특성은 C 언어로 작성 된 Windows API에 대 한 매우 가까운 매핑입니다. 또한 일반적으로 섞을 수 클래스 라이브러리에 대 한 호출 자유롭게 Windows API를 직접 호출 합니다. 그러나 이러한 직접 액세스, 뜻하지는지 않습니다는 클래스는 해당 API에 대 한 완전 한 대체 합니다. 개발자 해야 같은 일부 Windows 함수를 직접 호출을 수행할 가끔 여전히 [SetCursor](http://msdn.microsoft.com/library/windows/desktop/ms648393) 및 [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385), 예를 들어 있습니다. Windows 함수 분명 한 이점은 이렇게 하는 경우에 클래스 멤버 함수에 의해 래핑됩니다.  
  
 때로는 네이티브 Windows 함수를 호출 해야 하기 때문에 C 언어 Windows API 설명서에 액세스할 수 있어야 합니다. 이 설명서는 Microsoft Visual c + +에 포함 되어 있습니다.  
  
> [!NOTE]
>  MFC 라이브러리 프레임 워크 작동 하는 방법의 개요를 참조 하십시오. [클래스를 사용 하 여 Windows 용 응용 프로그램을](../mfc/using-the-classes-to-write-applications-for-windows.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [일반 클래스 디자인 원칙](../mfc/general-class-design-philosophy.md)
