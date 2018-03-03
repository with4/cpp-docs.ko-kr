---
title: "컴파일러 오류 C2097 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2097
dev_langs:
- C++
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e50154d88a5019cdc181c4921c09cbd222d8b530
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2097"></a>컴파일러 오류 C2097
초기화가 잘못 되었습니다  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  상수가 아닌 값을 사용 하 여 변수를 초기화 합니다.  
  
2.  긴 주소로 짧은 주소를 초기화 합니다.  
  
3.  로컬 구조체, 공용 구조체 또는 비상수 식 사용 하 여 컴파일할 때 사용 하 여 배열 초기화 **/Za**합니다.  
  
4.  쉼표 연산자를 포함 하는 식으로 초기화 합니다.  
  
5.  상수 또는 기호는 식으로 초기화 합니다.