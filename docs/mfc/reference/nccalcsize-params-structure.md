---
title: "NCCALCSIZE_PARAMS 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NCCALCSIZE_PARAMS
dev_langs:
- C++
helpviewer_keywords:
- NCCALCSIZE_PARAMS structure
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
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
ms.openlocfilehash: 88c25fd5e5862d5f0954ae853442c66eaf7320c8
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="nccalcsizeparams-structure"></a>NCCALCSIZE_PARAMS 구조체
`NCCALCSIZE_PARAMS` 응용 프로그램이 처리 하는 동안 사용할 수 있는 정보를 포함 하는 구조는 `WM_NCCALCSIZE` 크기, 위치 및 유효한 내용의 창의 클라이언트 영역을 계산 하는 메시지입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagNCCALCSIZE_PARAMS {  
    RECT rgrc[3];  
    PWINDOWPOS lppos;  
} NCCALCSIZE_PARAMS;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *rgrc*  
 사각형의 배열을 지정합니다. 첫 번째 이동 또는 크기 조정 된 창의 새 좌표가 포함 되어 있습니다. 두 번째를 이동 하거나 크기를 조정 하기 전에 창의 좌표를 포함 합니다. 세 번째를 이동 하거나 크기를 조정 하기 전에 창의 클라이언트 영역의 좌표를 포함 합니다. 창의 자식 창 이면 좌표가 부모 창의 클라이언트 영역을 기준으로 합니다. 최상위 창입니다, 좌표는 화면을 기준으로 합니다.  
  
 *lppos*  
 가리키는 [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) 이동 하거나 크기를 조정할 수 있는 창을 발생 시킨 작업에 지정 된 크기와 위치 값이 포함 된 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winuser.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)


