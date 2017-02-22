---
title: "컴파일러 경고(수준 4) C4435 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# 컴파일러 경고(수준 4) C4435
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class1': 가상 기본 'class2'\(으\)로 인해 \/vd2의 개체 레이아웃이 변경됩니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 기본 옵션 \/vd1을 컴파일, 파생된 클래스에 없는 한  `vtordisp`  지정된 가상 기본에 대한 필드가 없습니다.  \/vd2 또는  `#pragma vtordisp(2)`  가 사용 된  `vtordisp`  필드가 있는 개체 레이아웃 변경 됩니다.  서로 상호 작용 모듈은 컴파일해야 하는 경우 이진 호환성 문제가 발생할 수 있습니다  `vtordisp`  설정 합니다.  
  
## 예제  
 다음 샘플에서는 C4435 오류가 발생하는 경우를 보여 줍니다.  
  
```cpp  
// C4435.cpp  
// compile with: /c /W4  
#pragma warning(default : 4435)  
class A  
{  
public:  
    virtual ~A() {}  
};  
  
class B : public virtual A  // C4435  
{};  
```  
  
## 참고 항목  
 [vtordisp](../../preprocessor/vtordisp.md)   
 [\/vd\(생성 치환 비활성화\)](../../build/reference/vd-disable-construction-displacements.md)