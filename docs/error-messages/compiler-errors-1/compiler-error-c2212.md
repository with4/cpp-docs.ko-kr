---
title: 컴파일러 오류 C2212 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2212
dev_langs:
- C++
helpviewer_keywords:
- C2212
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 152b38be30b50684684bb0c2c39a035b748915b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33168739"
---
# <a name="compiler-error-c2212"></a>컴파일러 오류 C2212
'identifier': __based 함수에 대 한 포인터에 사용할 수 없습니다  
  
 함수에 대 한 포인터를 선언할 수 없습니다 `__based`합니다. 코드 기반 데이터를 유지 해야 하는 경우 사용 하 여는 `__declspec` 키워드 또는 `data_seg` pragma입니다.