---
title: COMPAREITEMSTRUCT 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COMPAREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- COMPAREITEMSTRUCT structure [MFC]
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a94d39c6b6c256444cd2850f7e55a7e4b87f6d7a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compareitemstruct-structure"></a>COMPAREITEMSTRUCT 구조체
`COMPAREITEMSTRUCT` 식별자 및 정렬 된, 소유자가 그린 목록 상자 또는 콤보 상자에 있는 두 항목에 대 한 응용 프로그램 제공 하는 데이터 구조를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagCOMPAREITEMSTRUCT {  
    UINT CtlType;  
    UINT CtlID;  
    HWND hwndItem;  
    UINT itemID1;  
    DWORD itemData1;  
    UINT itemID2;  
    DWORD itemData2;  
} COMPAREITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `CtlType`  
 **ODT_LISTBOX** (소유자 그리기 목록 상자의 지정) 또는 **ODT_COMBOBOX** (소유자 그리기 콤보 상자 지정).  
  
 `CtlID`  
 목록 상자 또는 콤보 상자 컨트롤 ID입니다.  
  
 `hwndItem`  
 컨트롤의 창 핸들입니다.  
  
 *itemID1*  
 목록 상자 또는 콤보 상자 비교 하 고 첫 번째 항목의 인덱스입니다.  
  
 *itemData1*  
 비교할 첫 번째 항목에 대 한 응용 프로그램에서 제공한 데이터입니다. 이 값 목록 또는 콤보 상자에 항목을 추가 하는 호출에 전달 되었습니다.  
  
 *itemID2*  
 목록 상자 또는 콤보 상자 비교 하 고 두 번째 항목의 인덱스입니다.  
  
 *itemData2*  
 비교할 두 번째 항목에 대 한 응용 프로그램에서 제공한 데이터입니다. 이 값 목록 또는 콤보 상자에 항목을 추가 하는 호출에 전달 되었습니다.  
  
## <a name="remarks"></a>설명  
 소유자가 그린 목록 상자에 새 항목을 추가 하는 응용 프로그램 또는 콤보 상자 사용 하 여 만든 때마다는 **CBS_SORT** 또는 **LBS_SORT** 스타일 보내는데 소유자는 `WM_COMPAREITEM` 메시지입니다. `lParam` 에 대 한 긴 포인터를 포함 하는 메시지의 매개 변수는 `COMPAREITEMSTRUCT` 구조입니다. 메시지를 받으면 소유자와 두 항목을 비교 다른 앞에 정렬 항목을 나타내는 값을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winuser.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)

