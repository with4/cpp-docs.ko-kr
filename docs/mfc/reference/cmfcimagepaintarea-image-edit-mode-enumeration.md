---
title: 'Cmfcimagepaintarea:: Image_edit_mode 열거형 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
dev_langs:
- C++
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b87b0c8c179e2982c450d244c50ea89dad2a596a
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848608"
---
# <a name="cmfcimagepaintareaimageeditmode-enumeration"></a>CMFCImagePaintArea::IMAGE_EDIT_MODE 열거형
이미지 편집기 대화 상자에서 이미지를 수정 하는 데 사용 하는 그리기 모드를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum IMAGE_EDIT_MODE  
{  
    IMAGE_EDIT_MODE_PEN = 0,  
    IMAGE_EDIT_MODE_FILL, 
    IMAGE_EDIT_MODE_LINE, 
    IMAGE_EDIT_MODE_RECT, 
    IMAGE_EDIT_MODE_ELLIPSE, 
    IMAGE_EDIT_MODE_COLOR 
};  
```  
  
## <a name="members"></a>멤버  
  
|||  
|-|-|  
|이름|설명|  
|IMAGE_EDIT_MODE_PEN|각 픽셀을 그리는 데 사용 합니다.|  
|IMAGE_EDIT_MODE_FILL|현재 커서 위치에 있는 색을 포함 하는 모든 인접 한 영역을 채우는 데 사용 합니다.|  
|IMAGE_EDIT_MODE_LINE|줄을 그리는 데 사용 합니다.|  
|IMAGE_EDIT_MODE_RECT|사각형을 그리는 데 사용 합니다.|  
|IMAGE_EDIT_MODE_ELLIPSE|타원을 그리는 데 사용 합니다.|  
|IMAGE_EDIT_MODE_COLOR|현재 커서 위치에 현재 색을 색으로 설정 하는 데 사용 합니다.|  
  
### <a name="remarks"></a>설명  
 합니다 `CMFCImagePaintArea` 고 `CMFCImageEditorDialog` 클래스 현재 그리기 모드를 설정 하려면이 열거형을 사용 합니다. 이미지 편집기 대화 상자 그림 영역을 수정 하는 그리기 모드와 현재 색 사용 됩니다. 에 대 한 자세한 내용은 `CMFCImagePaintArea` 하 고 `CMFCImageEditorDialog`를 참조 하세요 [CMFCImagePaintArea 클래스](../../mfc/reference/cmfcimagepaintarea-class.md) 및 [CMFCImageEditorDialog 클래스](../../mfc/reference/cmfcimageeditordialog-class.md)합니다.  
  
 IMAGE_EDIT_MODE_COLOR 그리기 모드를 사용 하 여 이미지에서 색을 선택 하면 프레임 워크 IMAGE_EDIT_MODE_PEN에 현재 그리기 모드를 설정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afximagepaintarea.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCImagePaintArea 클래스](../../mfc/reference/cmfcimagepaintarea-class.md)   
 [CMFCImageEditorDialog 클래스](../../mfc/reference/cmfcimageeditordialog-class.md)
