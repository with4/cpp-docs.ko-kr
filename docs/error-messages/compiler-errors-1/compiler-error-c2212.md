---
title: "컴파일러 오류 C2212 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2212
dev_langs:
- C++
helpviewer_keywords:
- C2212
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c49161940c1f382a8bf9d82a648cc4396a11e86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2212"></a>컴파일러 오류 C2212
'identifier': __based 함수에 대 한 포인터에 사용할 수 없습니다  
  
 함수에 대 한 포인터를 선언할 수 없습니다 `__based`합니다. 코드 기반 데이터를 유지 해야 하는 경우 사용 하 여는 `__declspec` 키워드 또는 `data_seg` pragma입니다.