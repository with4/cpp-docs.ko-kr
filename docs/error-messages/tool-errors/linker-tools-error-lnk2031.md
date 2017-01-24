---
title: "링커 도구 오류 LNK2031 | Microsoft Docs"
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
  - "LNK2031"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2031"
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK2031
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"function\_declaration" decorated\_name에 대해 p\/invoke를 생성할 수 없습니다. 메타데이터에 호출 규칙이 없습니다.  
  
 네이티브 함수를 순수 이미지로 가져오려는 경우 네이티브 컴파일과 순수 컴파일 사이에 암시적 호출 규칙이 서로 다르다는 점을 기억해야 합니다.  순수 이미지에 대한 자세한 내용은 [순수형 및 안정형 코드](../../dotnet/pure-and-verifiable-code-cpp-cli.md)를 참조하십시오.  
  
## 예제  
 이 코드 샘플에서는 [\_\_cdecl](../../cpp/cdecl.md)을 사용하여 해당 호출 규칙을 암시적으로 지정하고 내보낸 네이티브 함수로 구성 요소를 생성합니다.  
  
```  
// LNK2031.cpp  
// compile with: /LD  
extern "C" {  
   __declspec(dllexport) int func() { return 3; }  
};  
```  
  
## 예제  
 다음 샘플에서는 네이티브 함수를 사용하는 순수 클라이언트를 만듭니다.  그러나 **\/clr:pure**를 사용하는 경우 호출 규칙은 [\_\_clrcall](../../cpp/clrcall.md)입니다.  다음 샘플에서는 LNK2031 오류가 생성됩니다.  
  
```  
// LNK2031_b.cpp  
// compile with: /clr:pure LNK2031.lib  
// LNK2031 expected  
extern "C" int func();  
  
int main() {  
   return func();  
}  
```  
  
## 예제  
 다음 샘플에서는 순수 이미지에서 네이티브 함수를 사용하는 방법을 보여 줍니다.  특히 명시적 **\_\_cdecl** 호출 규칙 지정자에 주목할 필요가 있습니다.  
  
```  
// LNK2031_c.cpp  
// compile with: /clr:pure LNK2031.lib  
extern "C" int __cdecl func();  
  
int main() {  
   return func();  
}  
```