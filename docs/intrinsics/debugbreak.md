---
title: "__debugbreak | Microsoft Docs"
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
  - "__debugbreak_cpp"
  - "__debugbreak"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__debugbreak 내장"
  - "중단점, __debugbreak 내장"
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __debugbreak
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 코드에서 중단점이 발생하며 사용자에게 디버거를 실행하라는 메시지가 표시됩니다.  
  
## 구문  
  
```  
void __debugbreak();  
```  
  
## 요구 사항  
  
|내장 함수|아키텍처|Header|  
|-----------|----------|------------|  
|`__debugbreak`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
  
## 설명  
 [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297.aspx)와 유사하게 `__debugbreak` 컴파일러 내장은 중단점을 발생시키는 이식 가능한 Win32 방식입니다.  
  
> [!NOTE]
>  **\/clr**을 사용하여 컴파일하는 경우 `__debugbreak`가 포함된 함수가 MSIL로 컴파일됩니다.  `asm int 3`은 함수를 네이티브로 컴파일하도록 합니다.  자세한 내용은 [\_\_asm](../assembler/inline/asm.md)을 참조하십시오.  
  
 예를 들면 다음과 같습니다.  
  
```  
main() {  
   __debugbreak();  
}  
```  
  
 위의 예는 아래 예와 유사합니다.  
  
```  
main() {  
   __asm {  
      int 3  
   }  
}  
```  
  
 x86 컴퓨터의 경우  
  
 이 루틴은 내장 루틴으로만 사용할 수 있습니다.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)