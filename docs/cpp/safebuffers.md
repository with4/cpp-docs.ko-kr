---
title: "safebuffer | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "safebuffers"
  - "safebuffers_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec 키워드(C++), safebuffers"
  - "safebuffers __declspec 키워드"
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# safebuffer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 함수에 대한 버퍼 오버런 보안 검사를 삽입하지 않도록 컴파일러에 지시합니다.  
  
## 구문  
  
```  
__declspec( safebuffers )  
```  
  
## 설명  
 **\/GS** 컴파일러 옵션은 스택에 보안 검사를 삽입해서 컴파일러가 버퍼 오버런을 테스트하도록 합니다.  보안 검사에 적합한 데이터 구조의 유형이 [\/GS\(버퍼 보안 검사\)](../build/reference/gs-buffer-security-check.md)에 묘사되어 있습니다.  버퍼 오버런 감지에 대한 자세한 내용은 MSDN 웹 사이트에서 [컴파일러 보안 심층 검사](http://go.microsoft.com/fwlink/?linkid=7260)를 참조하십시오.  
  
 전문가 수동 코드 검토 또는 외부 분석이 함수가 버퍼 오버런으로부터 안전한지 확인할 수 있습니다.  이 경우, 함수 선언에 \_\_`declspec(safebuffers)` 키워드를 적용하여 함수에 대한 보안 검사를 억제할 수 있습니다.  
  
> [!CAUTION]
>  그러나 버퍼 보안 검사는 중요한 보안 보호를 제공하고 성능에 별다른 영향을 미치지 않으므로,  함수의 성능이 매우 중요하고 해당 함수의 안전성이 파악되는 드문 경우를 제외하고, 버퍼 보안 검사를 억제하지 않도록 권장합니다.  
  
## 인라인 함수  
 *기본 함수*는 [inlining](../misc/inline-inline-forceinline.md) 키워드를 사용하여 *보조 함수*의 복사본을 삽입할 수 있습니다.  \_\_`declspec(safebuffers)` 키워드가 함수에 적용될 경우 해당 함수에 대해 버퍼 오버런 감지가 억제됩니다.  하지만 인라인닝은 다음 방식으로 \_\_`declspec(safebuffers)` 키워드에 영향을 줍니다.  
  
 **\/GS** 컴파일러 옵션이 두 가지 함수에 지정되었지만 기본 함수가 \_\_`declspec(safebuffers)` 키워드를 지정한다고 가정합니다.  보조 함수의 데이터 구조는 보안 검사를 가능하게 하기 때문에 이 함수는 보안 검사를 억제하지 않습니다.  이 경우 다음과 같은 결과가 나타납니다.  
  
-   컴파일러 최적화에 관계없이 컴파일러가 해당 함수를 인라인 처리하도록 보조 함수에 [\_\_forceinline](../misc/inline-inline-forceinline.md) 키워드를 지정합니다.  
  
-   보조 함수는 보안 검사에 적합하기 때문에 \_\_`declspec(safebuffers)` 키워드가 지정된 기본 함수에도 보안 검사가 적용됩니다.  
  
## 예제  
 다음 코드에서는 \_\_`declspec(safebuffers)`  키워드를 사용하는 방법을 보여 줍니다.  
  
```  
// compile with: /c /GS  
typedef struct {  
    int x[20];  
} BUFFER;  
static int checkBuffers() {  
    BUFFER cb;  
    // Use the buffer...  
    return 0;  
};  
static __declspec(safebuffers)   
    int noCheckBuffers() {  
    BUFFER ncb;  
    // Use the buffer...  
    return 0;  
}  
int wmain() {  
    checkBuffers();  
    noCheckBuffers();  
    return 0;  
}  
```  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [inline, \_\_inline, \_\_forceinline](../misc/inline-inline-forceinline.md)   
 [strict\_gs\_check](../preprocessor/strict-gs-check.md)