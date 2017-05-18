---
title: "DELETEITEMSTRUCT 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DELETEITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DELETEITEMSTRUCT structure
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f5936cbb863cf8ace851609cb1dc8352e21f9456
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

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
 `CtlType`  
 지정 **ODT_LISTBOX** (소유자가 그린 목록 상자) 또는 **ODT_COMBOBOX** (소유자가 그린 콤보 상자).  
  
 `CtlID`  
 목록 상자 또는 콤보 상자의 식별자를 지정합니다.  
  
 `itemID`  
 제거 하 고 콤보 상자나 목록 상자에 있는 항목의 인덱스를 지정 합니다.  
  
 `hwndItem`  
 컨트롤을 식별합니다.  
  
 `itemData`  
 항목에 대 한 응용 프로그램 정의 데이터를 지정합니다. 이 값은 컨트롤에 전달 된 **lParam** 목록 상자 또는 콤보 상자에는 항목을 추가 하는 메시지의 매개 변수입니다.  
  
## <a name="remarks"></a>주의  
 항목이 제거 되는 목록 상자 또는 콤보 상자 또는 콤보 상자나 목록 상자 소멸 될 때를 보내는데는 `WM_DELETEITEM` 삭제 된 각 항목에 대 한 소유자에 게는 메시지입니다. **lParam** 메시지의 매개 변수는이 구조에 대 한 포인터를 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)



