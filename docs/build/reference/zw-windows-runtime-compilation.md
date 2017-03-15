---
title: "/ZW(Windows Runtime 컴파일) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.CompileAsWinRT"
  - "/zw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ZW"
  - "/ZW 컴파일러 옵션"
  - "Windows 런타임 컴파일러 옵션"
  - "-ZW"
  - "-ZW 컴파일러 옵션"
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /ZW(Windows Runtime 컴파일)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱을 만드는 데 [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)]\([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]\)를 지원하도록 소스 코드를 컴파일합니다.  
  
 **\/ZW**를 사용하여 컴파일하는 경우에는 항상 **\/EHsc**도 지정합니다.  
  
## 구문  
  
```cpp  
/ZW /EHsc /ZW:nostdlib /EHsc  
```  
  
## 인수  
 nostdlib  
 Platform.winmd, Windows.Foundation.winmd 및 기타 기본 Windows 메타데이터\(.winmd\) 파일이 컴파일에 자동으로 포함되지 않음을 나타냅니다.  대신 [\/FU \(Name Forced \#using File\)](../../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션을 사용하여 Windows 메타데이터 파일을 명시적으로 지정해야 합니다.  
  
## 설명  
 **\/ZW** 옵션을 지정하는 경우 컴파일러에서는 다음과 같은 기능을 지원합니다.  
  
-   [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행하는 데 앱에 필요한 필수 메타데이터 파일, 네임스페이스, 데이터 형식 및 함수  
  
-   [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] 개체의 자동 참조 계산 및 참조 개수가 0이 되는 경우 개체의 자동 삭제  
  
 Incremental linker는 **\/ZW** 옵션을 사용하여 .obj 파일에 포함된 Windows 메타데이터를 지원하지 않으므로 [\/Gm\(최소 다시 빌드 사용\)](../../build/reference/gm-enable-minimal-rebuild.md) 옵션은 **\/ZW**와 호환되지 않습니다.  
  
 자세한 내용은 [Visual C\+\+ 언어 참조](../Topic/Visual%20C++%20Language%20Reference%20\(C++-CX\).md)을 참조하십시오.  
  
## 요구 사항  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)