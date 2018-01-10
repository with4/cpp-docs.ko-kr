---
title: "컴파일러 경고 (수준 1) C4691 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4691
dev_langs: C++
helpviewer_keywords: C4691
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17673ee3e65d2e0cd0d989c56759b62de38f5fdc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4691"></a>컴파일러 경고(수준 1) C4691
'type': 참조 하는 형식이 참조 되지 않은 어셈블리 'file'를 대신 사용 하는 현재 변환 단위에 정의 된 형식에에서 필요  
  
 원래 형식 정의 포함 하는 메타 데이터 파일 참조 되지 않은 하 고 컴파일러에서 지역 형식 정의 사용 하는 키를 누릅니다.  
  
 여기서 다시 작성 하는 경우에서 *파일*, C4691를 무시 하거나 pragma 해제 수 [경고](../../preprocessor/warning.md)합니다.  즉, 작성 하는 파일의 위치에 파일 컴파일러 형식 정의를 찾을 같습니다 C4691를 무시할 수 있습니다.  
  
 그러나, 컴파일러 아니라 메타 데이터에서 참조 되는 동일한 어셈블리는 정의 사용 하는 경우 예기치 않은 동작이 발생할 수 있습니다. CLR 형식은 형식의 이름 뿐만 아니라 어셈블리에 의해 형식화 됩니다.  즉, z.dll 어셈블리에서에서 형식을 Z는 y.dll 어셈블리에서에서 형식을 Z와 다릅니다.  
  
## <a name="example"></a>예  
 이 샘플은 원래 형식 정의 포함 합니다.  
  
```  
// C4691_a.cpp  
// compile with: /clr /LD /W1  
public ref class Original_Type {};  
```  
  
## <a name="example"></a>예  
 이 샘플 C4691_a.dll 참조 하 고 Original_Type 형식의 필드를 선언 합니다.  
  
```  
// C4691_b.cpp  
// compile with: /clr /LD  
#using "C4691_a.dll"  
public ref class Client {  
public:  
   Original_Type^ ot;  
};  
```  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4691 오류가 발생 합니다.  이 샘플은 Original_Type에 대 한 정의 포함 하며 C4691a.dll 참조 하지 않습니다 확인 합니다.  
  
 를 해결 하려면 원래 형식 정의 포함 하는 메타 데이터 파일을 참조 하 고 로컬 선언 및 정의 제거 합니다.  
  
```  
// C4691_c.cpp  
// compile with: /clr /LD /W1  
// C4691 expected  
  
// Uncomment the following line to resolve.  
// #using "C4691_a.dll"  
#using "C4691_b.dll"  
  
// Delete the following line to resolve.  
ref class Original_Type;  
  
public ref class MyClass : Client {};  
```