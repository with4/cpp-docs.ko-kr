---
title: "/CLRHEADER | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/CLRHEADER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRHEADER dumpbin 옵션"
  - "CLRHEADER dumpbin 옵션"
  - "-CLRHEADER dumpbin 옵션"
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /CLRHEADER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/CLRHEADER file  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `file`  
 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)로 빌드된 이미지 파일입니다.  
  
## 설명  
 CLRHEADER는 관리되는 모든 프로그램에서 사용하는 .NET 헤더 정보를 표시합니다.  출력은 .NET 헤더 및 헤더 섹션의 위치와 크기를 바이트 단위로 보여 줍니다.  
  
 [\/HEADERS](../../build/reference/headers.md) DUMPBIN 옵션은 [\/GL](../../build/reference/gl-whole-program-optimization.md) 컴파일러 옵션으로 만든 파일에만 사용할 수 있습니다.  
  
 \/CLR을 사용하여 컴파일한 파일에 대해 \/CLRHEADER를 사용하는 경우 dumpbin 출력에 **clr Header:** 섹션이 생성됩니다.  **플래그**의 값은 사용된 \/clr 옵션을 가리킵니다.  
  
-   0  \-\- \/clr \(이미지에 네이티브 코드가 포함될 수 있습니다.\)  
  
-   1 \-\- \/clr:safe \(이미지가 MSIL 전용입니다. 임의의 CLR 플랫폼에서 이미지를 실행할 수 있고 안전성을 확인할 수도 있습니다.\)  
  
-   3 \-\- \/clr:pure \(이미지가 MSIL 전용이지만 x86 플랫폼에서만 실행할 수 있습니다.\)  
  
 공용 언어 런타임에 대해 이미지가 빌드되었는지 여부를 프로그래밍 방식으로 검사할 수도 있습니다.  자세한 내용은 [방법: 이미지가 네이티브인지 CLR인지 확인](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)을 참조하십시오.  
  
## 참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)