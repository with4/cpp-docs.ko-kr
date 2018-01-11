---
title: "codecvt_utf16 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: codecvt/std::codecvt_utf16
dev_langs: C++
helpviewer_keywords: codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6d7746369c5ecb559cae3b787b8bbf2f475ba28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="codecvtutf16"></a>codecvt_utf16
UCS-2 또는 UCS-4로 인코드된 와이드 문자와 UTF-16LE 또는 UTF-16BE로 인코드된 바이트 스트림 간에 변환되는 [로캘](../standard-library/locale-class.md) 패싯을 나타냅니다.

```
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```
## <a name="parameters"></a>매개 변수
`Elem`  
와이드 문자 요소 형식입니다.  
`Maxcode`  
로캘 패싯에 대한 최대 문자 수입니다.  
`Mode`  
로캘 패싯에 대한 구성 정보입니다.  

## <a name="remarks"></a>설명
이 템플릿 클래스는 UCS-2 또는 UCS-4로 인코드된 와이드 문자와 UTF-16LE(Mode 및 little_endian인 경우) 또는 UTF-16BE(그 외의 경우)로 인코드된 바이트 스트림 간에 변환됩니다.

바이트 스트림은 이진 파일에 작성해야 하며, 텍스트 파일에 작성하는 경우 손상될 수 있습니다.

## <a name="requirements"></a>요구 사항
헤더: \<codecvt> 네임스페이스: std