---
title: "컴파일러 경고 (수준 1) C4407 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4407"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4407"
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4407
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

멤버에 대해 표현이 다른 포인터를 캐스팅합니다. 컴파일러가 잘못된 코드를 생성한 것 같습니다.  
  
 잘못된 캐스트를 발견했습니다.  
  
 Visual C\+\+ 2005에서 적용된 컴파일러 규칙으로 인해 C4407이 발생할 수 있습니다.  이제 멤버 포인터에 정규화된 이름과 연산자 주소\(&\)가 필요합니다.  
  
 C4407은 다중 상속 멤버에 대한 포인터와 단일 상속 멤버에 대한 포인터 사이에 캐스팅하는 경우에도 발생할 수 있습니다.  경우에 따라서는 이와 같이 캐스팅할 수도 있지만 단일 상속 멤버 포인터 표현에 충분한 정보가 들어 있지 않으면 이를 수행할 수 없습니다.  이 경우 **\/vmm**을 사용하여 컴파일하는 것이 좋습니다. 자세한 내용은 [\/vmm, \/vms, \/vmv\(일반적인 용도 표시\)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)를 참조하십시오.  기본 클래스를 다시 정렬해 볼 수도 있습니다. 파생 클래스에서 0이 아닌 오프셋에 기본 클래스가 있으면 컴파일러가 변환 시 정보 소실을 감지합니다.  
  
 다음 샘플에서는 C4407 오류가 발생하는 경우를 보여 줍니다.  
  
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