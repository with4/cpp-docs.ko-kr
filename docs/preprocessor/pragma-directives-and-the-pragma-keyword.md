---
title: "Pragma 지시문 및 __Pragma 키워드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#pragma"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#pragma 지시문, C/C++"
  - "__pragma 키워드"
  - "pragma 지시문(#pragma)"
  - "pragma 지시문, C/C++"
  - "pragma"
  - "pragma, C/C++"
  - "전처리기"
  - "전처리기, pragma"
ms.assetid: 9867b438-ac64-4e10-973f-c3955209873f
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Pragma 지시문 및 __Pragma 키워드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pragma 지시문이 컴퓨터 또는 운영 체제 관련 컴파일러 기능을 지정합니다.  Microsoft 컴파일러 전용인 `__pragma` 키워드를 사용하여 매크로 정의 안에 pragma 지시문을 코딩할 수 있습니다.  
  
## 구문  
  
```  
  
      #pragma token-string  
__pragma(token-string)  
```  
  
## 설명  
 C 및 C\+\+의 각 구현은 호스트 컴퓨터나 운영 체제에 고유한 기능을 몇 가지 지원합니다.  예를 들어, 일부 프로그램은 데이터가 저장되는 메모리 영역을 정확하게 제어하거나 특정 함수가 매개 변수를 수신하는 방법을 제어해야 합니다.  `#pragma` 지시문을 사용하면 C 및 C\+\+ 언어와 전체적인 호환성을 유지하면서 컴파일러가 컴퓨터 및 운영 체제별 기능을 제공할 수 있습니다.  
  
 Pragma는 정의에 따라 컴퓨터 전용이거나 운영 체제 전용이며 대개 컴파일러마다 다릅니다.  Pragma를 조건문에 사용하여 새로운 전처리기 기능을 제공하거나 구현 정의 정보를 컴파일러에 제공할 수 있습니다.  
  
 `token-string`은 특정 컴파일러 명령과 인수를 제공하는\(있을 경우\) 일련의 문자입니다.  pragma가 포함된 줄에서 숫자 기호\(**\#**\)가 공백이 아닌 첫 번째 문자여야 합니다. 공백 문자로 숫자 기호와 단어 "pragma"를 구분할 수 있습니다.  `#pragma` 뒤에는 변환기가 전처리 토큰으로 구문 분석할 수 있는 텍스트를 씁니다.  `#pragma`의 인수에는 매크로 확장이 적용됩니다.  
  
 컴파일러가 인식할 수 없는 pragma를 찾으면 경고를 표시하고 컴파일을 계속합니다.  
  
 Microsoft C 및 C\+\+ 컴파일러는 다음 pragma를 인식합니다.  
  
||||  
|-|-|-|  
|[alloc\_text](../preprocessor/alloc-text.md)|[auto\_inline](../preprocessor/auto-inline.md)|[bss\_seg](../preprocessor/bss-seg.md)|  
|[check\_stack](../preprocessor/check-stack.md)|[code\_seg](../preprocessor/code-seg.md)|[comment](../preprocessor/comment-c-cpp.md)|  
|[component](../preprocessor/component.md)|[conform](../preprocessor/conform.md) <sup>1</sup>|[const\_seg](../preprocessor/const-seg.md)|  
|[data\_seg](../preprocessor/data-seg.md)|[deprecated](../preprocessor/deprecated-c-cpp.md)|[detect\_mismatch](../preprocessor/detect-mismatch.md)|  
|[fenv\_access](../preprocessor/fenv-access.md)|[float\_control](../preprocessor/float-control.md)|[fp\_contract](../preprocessor/fp-contract.md)|  
|[function](../preprocessor/function-c-cpp.md)|[hdrstop](../preprocessor/hdrstop.md)|[include\_alias](../preprocessor/include-alias.md)|  
|[init\_seg](../preprocessor/init-seg.md) <sup>1</sup>|[inline\_depth](../preprocessor/inline-depth.md)|[inline\_recursion](../preprocessor/inline-recursion.md)|  
|[intrinsic](../preprocessor/intrinsic.md)|[loop](../preprocessor/loop.md) <sup>1</sup>|[make\_public](../preprocessor/make-public.md)|  
|[managed](../preprocessor/managed-unmanaged.md)|[message](../preprocessor/message.md)||  
|[omp](../preprocessor/omp.md)|[once](../preprocessor/once.md)||  
|[optimize](../preprocessor/optimize.md)|[pack](../preprocessor/pack.md)|[pointers\_to\_members](../preprocessor/pointers-to-members.md) <sup>1</sup>|  
|[pop\_macro](../preprocessor/pop-macro.md)|[push\_macro](../preprocessor/push-macro.md)|[region, endregion](../preprocessor/region-endregion.md)|  
|[runtime\_checks](../preprocessor/runtime-checks.md)|[section](../preprocessor/section.md)|[setlocale](../preprocessor/setlocale.md)|  
|[strict\_gs\_check](../preprocessor/strict-gs-check.md)|[unmanaged](../preprocessor/managed-unmanaged.md)|[vtordisp](../preprocessor/vtordisp.md) <sup>1</sup>|  
|[warning](../preprocessor/warning.md)|||  
  
 1.  C\+\+ 컴파일러에서만 지원됩니다.  
  
## Pragma 및 컴파일러 옵션  
 일부 pragma는 컴파일러 옵션과 같은 기능을 제공합니다.  소스 코드에 pragma가 발생하면 컴파일러 옵션에 지정된 동작을 재정의합니다.  예를 들어, [\/Zp8](../build/reference/zp-struct-member-alignment.md)을 지정한 경우 [pack](../preprocessor/pack.md) 코드의 특정 섹션에 대해 이 컴파일러 설정을 재정의할 수 있습니다.  
  
```  
cl /Zp8 ...  
  
<file> - packing is 8  
// ...  
#pragma pack(push, 1) - packing is now 1  
// ...  
#pragma pack(pop) - packing is 8  
</file>  
```  
  
## \_\_pragma\(\) 키워드  
 **Microsoft 전용**  
  
 컴파일러는 `#pragma` 지시문과 기능이 같지만 매크로 정의에서 인라인으로 사용할 수 있는 `__pragma` 키워드를 지원합니다.  컴파일러는 지시문의 숫자 기호 문자\('\#'\)를 [stringizing 연산자\(\#\)](../preprocessor/stringizing-operator-hash.md)로 해석하기 때문에 매크로 정의에서 `#pragma` 지시문을 사용할 수 없습니다.  
  
 다음 코드 예제에서는 `__pragma` 키워드를 매크로에서 사용하는 방법을 보여 줍니다.  이 코드는 "컴파일러 COM 지원 샘플"의 ACDUAL 샘플에 있는 mfcdual.h 헤더에서 발췌되었습니다.  
  
```  
#define CATCH_ALL_DUAL \  
CATCH(COleException, e) \  
{ \  
_hr = e->m_sc; \  
} \  
AND_CATCH_ALL(e) \  
{ \  
__pragma(warning(push)) \  
__pragma(warning(disable:6246)) /*disable _ctlState prefast warning*/ \  
AFX_MANAGE_STATE(pThis->m_pModuleState); \  
__pragma(warning(pop)) \  
_hr = DualHandleException(_riidSource, e); \  
} \  
END_CATCH_ALL \  
return _hr; \  
```  
  
 **End Microsoft 전용**  
  
## 참고 항목  
 [C\/C\+\+ 전처리기 참조](../preprocessor/c-cpp-preprocessor-reference.md)   
 [C Pragma](../c-language/c-pragmas.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)