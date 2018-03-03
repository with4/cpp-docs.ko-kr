---
title: "인쇄 | Microsoft Docs"
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
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01ee396a7866179bd140f203192d1bdcbfb4681e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="printing"></a>인쇄
Microsoft Windows 장치 독립적 디스플레이 구현합니다. Mfc에서 즉 동일한 그리기 호출에는 `OnDraw` 뷰 클래스의 멤버 함수는 디스플레이 프린터와 같은 다른 장치에서 그리기를 담당 합니다. 인쇄 미리 보기에 대 한 대상 장치는 화면에는 시뮬레이션 된 프린터 출력 합니다.  
  
##  <a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a>프레임 워크의 역할 및 인쇄에서의 역할  
 뷰 클래스에는 다음 책임이 있습니다.  
  
-   얼마나 많은 페이지가 문서에 사용 되는 프레임 워크에 게 알립니다.  
  
-   지정된 된 페이지를 인쇄 하려면을 묻는 메시지가 나타나면 문서의 해당 부분을 그립니다.  
  
-   할당 하 고 모든 글꼴 또는 인쇄에 필요한 기타 그래픽 장치 GDI (인터페이스) 리소스 할당을 취소 합니다.  
  
-   필요에 따라 전송 하면 이스케이프 코드 예를 들어 지정된 된 페이지를 인쇄 하기 전에 프린터 모드를 변경 하려면를 페이지 별로에서 인쇄 된 방향을 변경 합니다.  
  
 프레임 워크의 역할은 다음과 같습니다.  
  
-   표시는 **인쇄** 대화 상자.  
  
-   만들기는 [CDC](../mfc/reference/cdc-class.md) 프린터에 대 한 개체입니다.  
  
-   호출 된 [StartDoc](../mfc/reference/cdc-class.md#startdoc) 및 [EndDoc](../mfc/reference/cdc-class.md#enddoc) 의 멤버 함수는 `CDC` 개체입니다.  
  
-   반복 해 서 호출 된 [StartPage](../mfc/reference/cdc-class.md#startpage) 의 멤버 함수는 `CDC` 개체, 페이지 인쇄 하 고 호출 뷰 클래스에 게 알립니다는 [EndPage](../mfc/reference/cdc-class.md#endpage) 의 멤버 함수는 `CDC` 개체입니다.  
  
-   적절 한 시간에 뷰에서 재정의 가능한 함수를 호출 합니다.  
  
 다음 문서 프레임 워크에서 인쇄 및 인쇄 미리 보기를 지원 하는 방법을 설명 합니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [기본 인쇄가 수행 되는 방법](../mfc/how-default-printing-is-done.md)  
  
-   [다중 페이지 문서](../mfc/multipage-documents.md)  
  
-   [머리글 및 바닥글](../mfc/headers-and-footers.md)  
  
-   [인쇄를 위한 GDI 리소스 할당](../mfc/allocating-gdi-resources.md)  
  
-   [인쇄 미리 보기](../mfc/print-preview-architecture.md)  
  
## <a name="see-also"></a>참고 항목  
 [인쇄 및 인쇄 미리 보기](../mfc/printing-and-print-preview.md)

