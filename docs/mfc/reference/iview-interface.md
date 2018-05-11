---
title: IView 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
dev_langs:
- C++
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a06243af3de7a2f4b32aa9a9ae492dfe3b2d3b64
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="iview-interface"></a>IView 인터페이스
몇 가지 메서드를 구현 하는 [CWinFormsView](../../mfc/reference/cwinformsview-class.md) 를 사용 하는 관리 되는 컨트롤에 알림을 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
interface class IView  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IView::OnActivateView](#onactivateview)|뷰 활성화 또는 비활성화 하는 경우에 MFC에서 호출 됩니다.|  
|[IView::OnInitialUpdate](#oninitialupdate)|보기에는 문서에 처음 연결 되었으나 처음 표시 되는 보기 프레임 워크에서 호출 됩니다.|  
|[IView::OnUpdate](#onupdate)|문서 보기의; 수정한 후에 MFC에서 호출 합니다. 이 함수에서는 보기 수정 내용을 반영 하도록 표시를 업데이트 합니다.|  
  
## <a name="remarks"></a>설명  
 `IView` 몇 가지 메서드를 구현 하는 `CWinFormsView` 호스팅된 관리 되는 컨트롤에 공통 보기 알림을 전달할를 사용 하 여 합니다. 이들은 [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) 및 [OnActivateView](#onactivateview)합니다.  
  
 `IView` 유사한 [CView](../../mfc/reference/cview-class.md), 하지만 관리 되는 보기 및 컨트롤에만 사용 됩니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  

## <a name="requirements"></a>요구 사항  
 헤더: afxwinforms.h (atlmfc\lib\mfcmifc80.dll 어셈블리에에서 정의 됨)  

## <a name="onactivateview"></a> IView::OnActivateView  
뷰 활성화 또는 비활성화 하는 경우에 MFC에서 호출 됩니다.
```
void OnActivateView(bool activate);
```
## <a name="parameters"></a>매개 변수
`activate`  
보기를 새로 있는지 여부를 나타냅니다. 활성화 또는 비활성화 합니다.  

## <a name="oninitialupdate"></a> IView::OnInitialUpdate
보기에는 문서에 처음 연결 되었으나 처음 표시 되는 보기 프레임 워크에서 호출 됩니다.
```
void OnInitialUpdate();
```

## <a name="onupdate"></a> IView::OnUpdate 
문서 보기의 수정 된 후에 MFC에서 호출 됩니다.  
```
void OnUpdate();
```
## <a name="remarks"></a>설명  
이 함수에서는 보기 수정 내용을 반영 하도록 표시를 업데이트 합니다.

## <a name="see-also"></a>참고 항목  
 [CWinFormsView 클래스](../../mfc/reference/cwinformsview-class.md)   
 [CView 클래스](../../mfc/reference/cview-class.md)
