---
title: "컴파일러 경고 (수준 1) C4407 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4407
dev_langs: C++
helpviewer_keywords: C4407
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 736b5f99115d6e2a39ee77005c7b3248ac191453
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4407"></a>컴파일러 경고(수준 1) C4407
멤버 표현에 다른 포인터 캐스팅, 컴파일러 코드를 생성할 수 잘못 된  
  
 잘못 된 캐스팅 하는 검색 되었습니다.  
  
 Visual c + + 2005에서 수행 된 컴파일러 규칙 작업으로 인해 C4407은 생성할 수 있습니다. 이제 멤버 포인터에 정규화된 이름과 연산자 주소(&)가 필요합니다.  
  
 C4407 사이 다중 상속을 멤버 포인터는 단일 상속-멤버 포인터에 캐스팅 하는 경우에 발생할 수 있습니다. 경우에 따라이 작동할 수 하지만 경우에 따라 만들 수 없습니다 단일 상속 멤버 포인터 표현 충분 한 정보를 저장 하지 않습니다. 사용 하 여 컴파일하는 **/vmm** 도움이 될 수 있습니다 (자세한 내용은 참조 [/vmm, /vms, /vmv (일반적인 용도 표시)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)). 기본 클래스를 다시 정렬 시도해 볼 수 있습니다. 컴파일러 기본 클래스에서 파생 된 0이 아닌 오프셋에는 변환에 정보가 손실을 검색 됩니다.  
  
 다음 샘플에서는 C4407 오류가 생성 됩니다.  
  
```  
// C4407.cpp  
// compile with: /W1 /c  
struct C1 {};  
struct C2 {};  
struct C3 : C1, C2 {};  
  
typedef void(C3::*PMF_C3)();  
typedef void(C2::*PMF_C2)();  
  
PMF_C2 f1(PMF_C3 pmf) {  
   return (PMF_C2)pmf;   // C4407, change type of cast,  
   // or reverse base class inheritance of C3 (i.e. : C2, C1)  
}  
```