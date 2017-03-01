---
title: "Cdc:: enumobjects에 대 한 콜백 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::EnumObjects
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::EnumObjects
ms.assetid: 380088b1-88a5-4fb4-bbb5-dd9e8386572b
caps.latest.revision: 10
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
ms.openlocfilehash: e4b24b5f5333d5514b9fdf69d204bca5d7947d7a
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcenumobjects"></a>CDC::EnumObjects에 대한 콜백 함수
*ObjectFunc* 이름은 응용 프로그램 제공 하는 함수 이름에 대 한 자리 표시자입니다.  
  
## <a name="syntax"></a>구문  
  
```  
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,  
    LPSTR* lpData);
```  
  
#### <a name="parameters"></a>매개 변수  
 *lpszLogObject*  
 가리키는 [LOGPEN](../../mfc/reference/logpen-structure.md) 또는 [LOGBRUSH](../../mfc/reference/logbrush-structure.md) 개체의 논리적 특성에 대 한 정보를 포함 하는 데이터 구조입니다.  
  
 `lpData`  
 에 전달 되는 응용 프로그램에서 제공 하는 데이터를 가리키는 `EnumObjects` 함수입니다.  
  
## <a name="return-value"></a>반환 값  
 콜백 함수는 반환 된 `int`합니다. 이 반환 값은 사용자 정의입니다. 콜백 함수는 0을 반환 하는 경우 `EnumObjects` 열거형 일찍 중지 합니다.  
  
## <a name="remarks"></a>주의  
 실제 이름을 내보내야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Cdc:: enumobjects](../../mfc/reference/cdc-class.md#enumobjects)


