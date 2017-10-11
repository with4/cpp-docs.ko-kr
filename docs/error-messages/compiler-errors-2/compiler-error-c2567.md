---
title: "컴파일러 오류 C2567 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2567
dev_langs:
- C++
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1bbdc535f75230da05a92eb0498176da40e918ea
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2567"></a>컴파일러 오류 C2567
'file'에서 메타 데이터를 열 수 없습니다 파일 수 삭제 되었거나 이동 되었음을  
  
 소스에서 참조 되는 메타 데이터 파일 (으로 `#using`) 찾을 수 없습니다 동일한 디렉터리에 컴파일러 백 엔드 프로세스에 의해 컴파일러 프런트 엔드 프로세스로 했습니다. 참조 [#using 지시문](../../preprocessor/hash-using-directive-cpp.md) 자세한 정보에 대 한 합니다.  
  
 C2567로 컴파일할 경우 발생할 수 **/c** 하나에서 컴퓨터를 다른 컴퓨터에서 링크 타임 코드 생성을 시도 합니다. 자세한 내용은 참조 [/LTCG (링크 타임 코드 생성)](../../build/reference/ltcg-link-time-code-generation.md)).  
  
 또한 컴퓨터에 더 많은 메모리가 없습니다. 남은 나타낼 수 있습니다.  
  
 이 오류를 해결 하려면 빌드 프로세스의 모든 단계에 대 한 메타 데이터 파일을 동일한 디렉터리 위치에 있는지 확인 합니다.
