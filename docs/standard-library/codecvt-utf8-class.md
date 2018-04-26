---
title: codecvt_utf8 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
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
ms.workload:
- cplusplus
ms.openlocfilehash: 0aeb05c5868c1d97713e81f6f09430f64ded9d8b
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="codecvtutf8"></a>codecvt_utf8

UCS-2 또는 UCS-4로 인코드된 와이드 문자와 UTF-8로 인코드된 바이트 스트림 간에 변환되는 [로캘](../standard-library/locale-class.md) 패싯을 나타냅니다.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>매개 변수

`Elem` 와이드 문자 요소 형식입니다.
`Maxcode` 로캘 패싯에 대 한 문자의 최대 수입니다.
`Mode` 로캘 패싯에 대 한 구성 정보입니다.

## <a name="remarks"></a>설명

바이트 스트림은 이진 파일 또는 텍스트 파일에 작성할 수 있습니다.

## <a name="requirements"></a>요구 사항

헤더: <codecvt> 네임스페이스: std
