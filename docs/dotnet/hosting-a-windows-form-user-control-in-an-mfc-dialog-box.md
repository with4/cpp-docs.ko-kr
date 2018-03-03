---
title: "MFC 대화 상자에서 사용자 정의 컨트롤을 형성 하는 Windows 호스트 | Microsoft Docs"
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
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: da8e8a54947b329fe36eea5c80bdc13ba5cdfa74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅
MFC ActiveX 컨트롤의 특수 한 종류는 Windows Forms 컨트롤을 호스트 하 고 ActiveX 인터페이스, 속성 및 메서드를 사용 하 여 컨트롤와 통신 하는 <xref:System.Windows.Forms.Control> 클래스입니다. 컨트롤에서 작동 하려면.NET Framework 속성 및 메서드를 사용 하는 것이 좋습니다.  
  
 MFC와 함께 사용 되는 Windows Forms를 보여 주는 샘플 응용 프로그램을 참조 하십시오. [MFC 및 Windows Forms 통합](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)합니다.  
  
> [!NOTE]
>  현재 릴리스에서 `CDialogBar` 개체는 Windows Forms 컨트롤을 호스트할 수 없습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)  
  
 [방법: Windows Forms에서 DDX/DDV 데이터 바인딩 수행](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)  
  
 [방법: 네이티브 C++ 클래스에서 Windows Forms 이벤트 싱크](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)  
  
## <a name="reference"></a>참조  
 [CWinFormsControl 클래스](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog 클래스](../mfc/reference/cdialog-class.md) &#124; [CWnd 클래스](../mfc/reference/cwnd-class.md) &#124;<xref:System.Windows.Forms.Control>  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Windows Forms/MFC 프로그래밍의 차이점](../dotnet/windows-forms-mfc-programming-differences.md)   
 [Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [Windows Form 사용자 정의 컨트롤을 MFC 대화 상자로 호스팅](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)