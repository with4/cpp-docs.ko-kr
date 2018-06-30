---
title: DELETEITEMSTRUCT 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DELETEITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5c844ad428143c82e8214eab74262b326bf2c9a4
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123242"
---
# <a name="deleteitemstruct-structure"></a>DELETEITEMSTRUCT 구조체
`DELETEITEMSTRUCT` 구조 삭제 된 소유자가 그린 목록 상자 또는 콤보 상자 항목에 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagDELETEITEMSTRUCT { /* ditms */  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    HWND hwndItem;  
    UINT itemData;  
} DELETEITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *CtlType*  
 ODT_LISTBOX (소유자가 그린 목록 상자) 또는 ODT_COMBOBOX (소유자가 그린 콤보 상자)을 지정합니다.  
  
 *CtlID*  
 목록 상자 또는 콤보 상자의 식별자를 지정합니다.  
  
 *itemID*  
 목록 상자 또는 콤보 상자가 제거 되는 항목의 인덱스를 지정 합니다.  
  
 *hwndItem*  
 컨트롤을 식별합니다.  
  
 *itemData*  
 항목에 대 한 응용 프로그램 정의 데이터를 지정합니다. 이 값이 컨트롤에 전달 되는 *lParam* 목록 상자 또는 콤보 상자에 항목을 추가 하는 메시지의 매개 변수입니다.  
  
## <a name="remarks"></a>설명  
 목록 상자 또는 콤보 상자 또는 목록 상자 또는 콤보 상자가 제거 항목이 제거 되 면 Windows 삭제 된 각 항목에 대 한 소유자에 게 WM_DELETEITEM 메시지를 보냅니다. *lParam* 메시지의 매개 변수는이 구조에 대 한 포인터를 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)


