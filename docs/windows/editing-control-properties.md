---
title: "컨트롤 속성 편집 | Microsoft Docs"
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
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls, editing properties
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2baed8431501bfa5bf68313403c87a1fb9bccb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="editing-control-properties"></a>컨트롤 속성 편집
### <a name="to-edit-the-properties-of-a-control-or-controls"></a>컨트롤 또는 컨트롤의 속성을 편집 하려면  
  
1.  대화 상자에서 수정 하려는 컨트롤을 선택 합니다.  
  
    > [!NOTE]
    >  여러 컨트롤을 선택 하면 선택한 컨트롤에 공통 된 속성만 편집할 수 있습니다.  
  
2.  에 [속성 창](/visualstudio/ide/reference/properties-window), 컨트롤의 속성을 변경 합니다.  
  
    > [!NOTE]
    >  설정 하는 경우는 **비트맵** 단추, 라디오 단추 또는 확인란 컨트롤 같은 속성이 **True**, 스타일 BS_BITMAP 컨트롤에 대 한 구현 됩니다. 자세한 내용은 참조 [단추 스타일](../mfc/reference/styles-used-by-mfc.md#button-styles)합니다. 비트맵 컨트롤과 연결의 예제를 보려면 [CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap)합니다. 대화 상자 리소스 편집기에 있는 동안 비트맵 컨트롤에 나타나지 않습니다.  
  
### <a name="to-undo-changes-to-the-properties-of-a-control"></a>컨트롤의 속성 변경 내용을 실행 취소 하려면  
  
1.  대화 상자 편집기에서 컨트롤에 포커스가 있는지 확인 합니다.  
  
2.  선택 **실행 취소** 에서 **편집** 메뉴 (컨트롤에 포커스가 없으면는 **실행 취소** 명령에 사용할 수 없습니다).  
  
 관리 되는 프로젝트에 리소스를 추가 하는 내용은 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 요구 사항  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)

