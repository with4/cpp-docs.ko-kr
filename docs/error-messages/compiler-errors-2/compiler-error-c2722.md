---
title: "컴파일러 오류 C2722 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2722
dev_langs:
- C++
helpviewer_keywords:
- C2722
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f8526422129b1fe114974de1c7f95cb55117d99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2722"></a>컴파일러 오류 C2722
':: operator': 다음 연산자 명령을; 잘못 되었습니다. 'operator 연산자'를 사용 하 여  
  
 `operator` 문 가져오거나 다시 정의한 요소 `::new` 또는 `::delete`합니다. `new` 및 `delete` 는 전역 연산자 하므로 범위 결정 연산자 (`::`)은 의미가 없습니다. 제거는 `::` 연산자입니다.