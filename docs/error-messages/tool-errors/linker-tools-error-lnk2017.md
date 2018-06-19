---
title: 링커 도구 오류 LNK2017 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2017
dev_langs:
- C++
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 095423b5f2d86cef309ed4316ff72d195b11eb26
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33313074"
---
# <a name="linker-tools-error-lnk2017"></a>링커 도구 오류 LNK2017
/largeaddressaware: no 없이 잘못 된 '세그먼트' 'symbol' 재배치  
  
 32 비트 주소와 64 비트 이미지를 작성 하려고 합니다. 이렇게 하려면 다음을 수행 해야 합니다.  
  
-   고정된 로드 주소를 사용 합니다.  
  
-   3 g B에 이미지를 제한 합니다.  
  
-   지정 [/largeaddressaware: no](../../build/reference/largeaddressaware-handle-large-addresses.md)합니다.