---
title: "선언 및 정의 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 선언 및 정의 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 DLL 인터페이스는 시스템의 일부 프로그램에서 내보내지는 것으로 알려진 모든 항목\(함수 및 데이터\), 즉 **dllimport** 또는 `dllexport`로 선언되는 모든 항목을 참조합니다.  DLL 인터페이스에 포함된 모든 선언은 **dllimport** 또는 `dllexport` 특성을 지정해야 합니다.  그러나 정의는 `dllexport` 특성만 지정해야 합니다.  예를 들어, 다음 함수 정의는 컴파일러 오류를 생성합니다.  
  
```  
__declspec( dllimport ) int func() {   // Error; dllimport  
                                    // prohibited on definition.  
   return 1;  
}  
```  
  
 다음 코드도 오류를 생성합니다.  
  
```  
#define DllImport   __declspec( dllimport )  
  
__declspec( dllimport ) int i = 10;  // Error; this is a  
                                     // definition.  
```  
  
 그러나 다음은 올바른 구문입니다.  
  
```  
__declspec( dllexport ) int i = 10;     // Okay--export definition  
```  
  
 **dllimport**가 선언을 암시하는 반면 `dllexport`는 정의를 암시합니다.  `dllexport`에 `extern` 키워드를 사용하여 선언을 강제해야 합니다. 그렇지 않으면 정의가 암시됩니다.  따라서 다음 예제는 올바릅니다.  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
extern DllImport int k; // These are both correct and imply a  
DllImport int j;        // declaration.  
```  
  
 다음 예제를 보면 위의 예제를 쉽게 이해할 수 있습니다.  
  
```  
static __declspec( dllimport ) int l; // Error; not declared extern.  
  
void func() {  
    static __declspec( dllimport ) int s;  // Error; not declared  
                                           // extern.  
    __declspec( dllimport ) int m;         // Okay; this is a   
                                           // declaration.  
    __declspec( dllexport ) int n;         // Error; implies external  
                                           // definition in local scope.  
    extern __declspec( dllimport ) int i;  // Okay; this is a  
                                           // declaration.  
    extern __declspec( dllexport ) int k;  // Okay; extern implies  
                                           // declaration.  
    __declspec( dllexport ) int x = 5;     // Error; implies external  
                                           // definition in local scope.  
}  
```  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)