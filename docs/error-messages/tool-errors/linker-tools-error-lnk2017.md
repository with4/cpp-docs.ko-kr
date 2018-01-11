---
title: "링커 도구 오류 LNK2017 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2017
dev_langs: C++
helpviewer_keywords: LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9446cb72ba9380e57b014b32d9ae00f6e9e554d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2017"></a>링커 도구 오류 LNK2017
/largeaddressaware: no 없이 잘못 된 '세그먼트' 'symbol' 재배치  
  
 32 비트 주소와 64 비트 이미지를 작성 하려고 합니다. 이렇게 하려면 다음을 수행 해야 합니다.  
  
-   고정된 로드 주소를 사용 합니다.  
  
-   3 g B에 이미지를 제한 합니다.  
  
-   지정 [/largeaddressaware: no](../../build/reference/largeaddressaware-handle-large-addresses.md)합니다.