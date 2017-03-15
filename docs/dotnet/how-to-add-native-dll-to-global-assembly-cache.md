---
title: "방법: 전역 어셈블리 캐시에 네이티브 DLL 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL[C++], native"
  - "GAC(전역 어셈블리 캐시), 네이티브 DLL 로드"
  - "네이티브 DLL[C++]"
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 방법: 전역 어셈블리 캐시에 네이티브 DLL 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM이 아닌 네이티브 DLL을 전역 어셈블리 캐시에 추가할 수 있습니다.  
  
## 예제  
 **\/ASSEMBLYLINKRESOURCE**를 사용하면 어셈블리에 네이티브 DLL을 포함시킬 수 있습니다.  
  
 자세한 내용은 [\/ASSEMBLYLINKRESOURCE\(.NET Framework 리소스에 대한 링크\)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)을 참조하십시오.  
  
```  
/ASSEMBLYLINKRESOURCE:MyComponent.dll  
```  
  
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)