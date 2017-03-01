---
title: "Cdc:: graystring에 대 한 콜백 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::GrayString
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::GrayString
ms.assetid: 5217e183-df48-426b-931b-6245022ca36f
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
ms.openlocfilehash: 3ce3afefae9618420a8a97b27994c33604745677
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcgraystring"></a>CDC::GrayString에 대한 콜백 함수
*OutputFunc* 응용 프로그램에서 제공 하는 콜백 함수 이름에 대 한 자리 표시자입니다.  
  
## <a name="syntax"></a>구문  
  
```  
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,  
    LPARAM lpData,  
    int nCount);
```  
  
#### <a name="parameters"></a>매개 변수  
 `hDC`  
 최소한의 비트맵으로 메모리 장치 컨텍스트를 식별 너비와 높이에 지정 된 `nWidth` 및 `nHeight` 를 `GrayString`합니다.  
  
 `lpData`  
 그릴 문자열을 가리킵니다.  
  
 `nCount`  
 출력에 문자 수를 지정 합니다.  
  
## <a name="return-value"></a>반환 값  
 콜백 함수의 반환 값 이어야 **TRUE** ; 성공을 나타내기 위해 그렇지 않으면 **FALSE**합니다.  
  
## <a name="remarks"></a>주의  
 콜백 함수 (*OutputFunc*) 좌표 (0,&0;)를 기준으로 이미지를 그리기 해야 하지 않고 (*x*, *y*).  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Cdc:: graystring](../../mfc/reference/cdc-class.md#graystring)


