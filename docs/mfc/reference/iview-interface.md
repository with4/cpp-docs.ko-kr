---
title: "IView 인터페이스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IView
dev_langs:
- C++
helpviewer_keywords:
- views [MFC]
- IView class
- views, classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 9a8b5f2d9d123aa3032cb30ecdbdd1cd380b32f8
ms.lasthandoff: 02/24/2017

---
# <a name="iview-interface"></a>IView 인터페이스
몇 가지 메서드를 구현 하는 [CWinFormsView](../../mfc/reference/cwinformsview-class.md) 사용 하 여 관리 되는 컨트롤에 알림을 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
interface class IView  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IView::OnActivateView](#onactivateview)|뷰 활성화 되거나 비활성화 때 MFC에서 호출 합니다.|  
|[IView::OnInitialUpdate](#oninitialupdate)|프레임 워크에서 뷰를 먼저 문서에 연결한 후 전에 호출 처음 표시 되는 보기.|  
|[IView::OnUpdate](#onupdate)|보기의 문서가 수정 되었습니다; 한 후에 MFC에서 호출 합니다. 이 함수는 수정 내용을 반영 하도록 표시를 업데이트 보기를 허용 합니다.|  
  
## <a name="remarks"></a>주의  
 `IView`몇 가지 메서드를 구현 하는 `CWinFormsView` 호스팅된 관리 되는 컨트롤에 일반적인 보기 알림을 전달할를 사용 하 여 합니다. 이들은 [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) 및 [OnActivateView](#onactivateview)합니다.  
  
 `IView`유사한 [CView](../../mfc/reference/cview-class.md), 있지만 관리 되는 보기 및 컨트롤에만 사용 됩니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  

## <a name="requirements"></a>요구 사항  
 헤더: afxwinforms.h (atlmfc\lib\mfcmifc80.dll 어셈블리에에서 정의 됨)  

## <a name="a-nameonactivateviewa-iviewonactivateview"></a><a name="onactivateview"></a>IView::OnActivateView  
뷰 활성화 되거나 비활성화 때 MFC에서 호출 합니다.
```
void OnActivateView(bool activate);
```
## <a name="parameters"></a>매개 변수
`activate`  
보기를 새로 있는지 여부를 나타냅니다. 활성화 또는 비활성화 합니다.  

## <a name="a-nameoninitialupdatea-iviewoninitialupdate"></a><a name="oninitialupdate"></a>IView::OnInitialUpdate
프레임 워크에서 뷰를 먼저 문서에 연결한 후 전에 호출 처음 표시 되는 보기.
```
void OnInitialUpdate();
```

## <a name="a-nameonupdatea-iviewonupdate"></a><a name="onupdate"></a>IView::OnUpdate 
문서 보기의 수정 된 후에 MFC에서 호출 됩니다.  
```
void OnUpdate();
```
## <a name="remarks"></a>주의  
이 함수는 수정 내용을 반영 하도록 표시를 업데이트 보기를 허용 합니다.

## <a name="see-also"></a>참고 항목  
 [CWinFormsView 클래스](../../mfc/reference/cwinformsview-class.md)   
 [CView 클래스](../../mfc/reference/cview-class.md)

