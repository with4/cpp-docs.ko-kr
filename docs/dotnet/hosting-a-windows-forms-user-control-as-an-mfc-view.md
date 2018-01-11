---
title: "호스팅하는 Windows Forms 사용자 컨트롤을 MFC 뷰로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7e4e0b7bc081d3b16b3f9aa55719d298f710cdab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅
MFC을 MFC 뷰로에서 Windows Forms 사용자 정의 컨트롤을 호스팅할 CWinFormsView 클래스를 사용 합니다. MFC Windows Forms 뷰는 ActiveX 컨트롤입니다. 사용자 정의 컨트롤 기본 보기의 자식으로 호스트 되 고 기본 보기의 전체 클라이언트 영역을 차지 하지만 40gb.  
  
 최종 결과에서 사용 하는 모델과 비슷합니다는 [CFormView 클래스](../mfc/reference/cformview-class.md)합니다. Windows Forms 디자이너 및 런타임 풍부한 양식 기반 뷰를 활용할 수 있습니다.  
  
 뷰 MFC Windows Forms ActiveX 컨트롤 이기 때문에 없는 동일한 `hwnd` MFC 뷰로 합니다. 에 대 한 포인터를 변수로 전달할 수 없습니다도 [CView](../mfc/reference/cview-class.md) 보기. 일반적으로.NET Framework 메서드를 사용 하 여 Windows Forms 뷰를 사용 하 여 Win32에 크게 의존 합니다.  
  
 MFC와 함께 사용 되는 Windows Forms를 보여 주는 샘플 응용 프로그램을 참조 하십시오. [MFC 및 Windows Forms 통합](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)  
  
 [방법: Windows Forms 컨트롤에 명령 라우팅 추가](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)  
  
 [방법: Windows Forms 컨트롤의 속성 및 메서드 호출](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [방법: 복합 컨트롤 작성](/dotnet/framework/winforms/controls/how-to-author-composite-controls)