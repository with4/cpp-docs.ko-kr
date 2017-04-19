---
title: "codecvt_utf8 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- codecvt_utf8
- codecvt/std::codecvt_utf8
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf8 class
ms.assetid: 2a87478f-e2d4-4b8d-ad9c-00add01d1bb0
caps.latest.revision: 19
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 1f6c2724747d22aa662779fa8f6433647a7853f3
ms.lasthandoff: 02/24/2017

---
# <a name="codecvtutf8"></a>codecvt_utf8
UCS-2 또는 UCS-4로 인코드된 와이드 문자와 UTF-8로 인코드된 바이트 스트림 간에 변환되는 [로캘](../standard-library/locale-class.md) 패싯을 나타냅니다.

```
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>매개 변수

`Elem`  
와이드 문자 요소 형식입니다.  
`Maxcode`  
로캘 패싯에 대한 최대 문자 수입니다.  
`Mode`  
로캘 패싯에 대한 구성 정보입니다.  

## <a name="remarks"></a>설명

바이트 스트림은 이진 파일 또는 텍스트 파일에 작성할 수 있습니다.  

## <a name="requirements"></a>요구 사항

헤더: <codecvt> 네임스페이스: std

