---
title: SDI 및 MDI | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db63efe8d7e2622610bb56f5e6885b72b705093b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385806"
---
# <a name="sdi-and-mdi"></a>SDI 및 MDI
MFC를 사용 하면 쉽게 단일 문서 인터페이스 (SDI) 및 (mdi 다중) 다중 문서 인터페이스 응용 프로그램 모두와 작업할 수 있습니다.  
  
 SDI 응용 프로그램에는 한 번에 하나의 열려 있는 문서 프레임 창이 있습니다. MDI 응용 프로그램 여러 문서 프레임 창을 동일한 인스턴스에서 응용 프로그램의 열 수를 허용 합니다. MDI 응용 프로그램에 각각 포함 된 별도 문서 창에는 여러 개의 MDI 자식 창, 즉 자체로 프레임 창, 열려 있을 수 있습니다. 일부 응용 프로그램에서 windows 차트 및 스프레드시트 창과 같은 다른 형식의 자식 창의 수 있습니다. 이 경우 메뉴 모음 다양 한 종류의 MDI 자식 창이 활성화 될에 따라 변경할 수 있습니다.  
  
> [!NOTE]
>  Windows 95 이상 버전에서는 응용 프로그램은 일반적으로 SDI 하므로 운영 체제는 "문서 중심" 보기를 채택 했습니다.  
  
 자세한 내용은 참조 [문서, 뷰 및 프레임 워크](../mfc/documents-views-and-the-framework.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스를 사용하여 Windows 응용 프로그램 작성](../mfc/using-the-classes-to-write-applications-for-windows.md)
