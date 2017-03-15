---
title: "Cdc:: setabortproc에 대 한 콜백 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::SetAbortProc
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::SetAbortProc
ms.assetid: daa36d5d-15de-40fc-8d37-a865d06c4710
caps.latest.revision: 11
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
ms.openlocfilehash: 1ba16ea60d8b18abd1962ded2da7e11ff2ef09a1
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcsetabortproc"></a>CDC::SetAbortProc에 대한 콜백 함수
이름 *AbortFunc* 응용 프로그램 제공 하는 함수 이름에 대 한 자리 표시자입니다.  
  
## <a name="syntax"></a>구문  
  
```  
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,  
    int code);
```  
  
#### <a name="parameters"></a>매개 변수  
 *hPr*  
 장치 컨텍스트를 식별합니다.  
  
 `code`  
 오류가 발생 했습니다 있는지 여부를 지정 합니다. 오류가 발생 하지 않은 경우 0입니다. **SP_OUTOFDISK** 인쇄 관리자가 현재 디스크 공간이 부족 하 고 더 많은 디스크 공간이 응용 프로그램이 대기 하는 경우에 사용할 수 있게 됩니다. 경우 `code` 는 **SP_OUTOFDISK**, 응용 프로그램에서 인쇄 작업을 중단할 필요가 없습니다. 그렇지 않으면이 반환 되어야 하며 인쇄 관리자에 게 호출 하 여는 **PeekMessage** 또는 **GetMessage** Windows 함수입니다.  
  
## <a name="return-value"></a>반환 값  
 인쇄 작업을 계속 하면 0이 아니고 및 0 중단 처리기 함수의 반환 값이 취소 되는 경우.  
  
## <a name="remarks"></a>주의  
 설명 섹션에 설명 된 대로 실제 이름으로 내보내야 하며 [cdc:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Cdc:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc)


