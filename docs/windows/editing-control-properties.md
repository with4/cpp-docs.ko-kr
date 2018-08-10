---
title: 컨트롤 속성 편집 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls, editing properties
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bc7b555ee04b8739040e0ec9d53c3820c2e13f16
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648748"
---
# <a name="editing-control-properties"></a>컨트롤 속성 편집
### <a name="to-edit-the-properties-of-a-control-or-controls"></a>컨트롤 또는 컨트롤의 속성을 편집 하려면  
  
1.  대화 상자에서 수정 하려는 컨트롤을 선택 합니다.  
  
    > [!NOTE]
    >  여러 컨트롤을 선택 하면 선택한 컨트롤에 공통 된 속성만 편집할 수 있습니다.  
  
2.  에 [속성 창](/visualstudio/ide/reference/properties-window), 컨트롤의 속성을 변경 합니다.  
  
    > [!NOTE]
    >  설정한 경우 합니다 **비트맵** 단추, 라디오 단추 또는 확인란 컨트롤 같은 속성을 **True**, 스타일을 컨트롤에 대 한 BS_BITMAP 구현 됩니다. 자세한 내용은 [단추 스타일](../mfc/reference/styles-used-by-mfc.md#button-styles)합니다. 컨트롤을 사용 하 여 비트맵을 연결 하는 예제를 보려면 [CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap)합니다. 비트맵에 있는 동안 컨트롤에 표시 되지 것입니다 합니다 **대화 상자** 리소스 편집기입니다.  
  
### <a name="to-undo-changes-to-the-properties-of-a-control"></a>컨트롤의 속성 변경 내용을 실행 취소 하려면  
  
1.  컨트롤에 포커스를가지고 있는지 확인 합니다 **대화 상자** 편집기입니다.  
  
2.  선택 **실행 취소** 에서 합니다 **편집** 메뉴 (컨트롤에 포커스가 없는 경우는 **취소** 명령을 사용할 수 없게 됩니다).  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [연습: Windows Forms 지역화](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) 고[연습: ASP.NET에서 지역화에 리소스를 사용 하 여](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)입니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)