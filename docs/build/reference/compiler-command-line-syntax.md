---
title: "컴파일러 명령줄 구문 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러, 명령줄 구문"
  - "구문, CL 컴파일러 명령줄"
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 명령줄 구문
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL 명령줄에서는 다음과 같은 구문을 사용합니다.  
  
```  
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]  
```  
  
 다음 표에서는 CL 명령에 사용되는 입력 항목을 보여 줍니다.  
  
|Entry|의미|  
|-----------|--------|  
|*옵션*|하나 이상의 [CL 옵션](../../build/reference/compiler-options.md)입니다.  모든 옵션은 지정한 모든 소스 파일에 적용됩니다.  옵션 앞에는 슬래시\(\/\)나 대시\(–\)가 붙습니다.  옵션에 인수가 있으면 옵션과 인수 사이에 공백을 사용해도 되는지를 확인할 수 있는 해당 옵션에 대한 설명이 표시됩니다.  \/HELP를 제외한 옵션 이름은 대\/소문자를 구분합니다.  자세한 내용은 [CL 옵션 순서](../../build/reference/order-of-cl-options.md)를 참조하십시오.|  
|`file`|하나 이상의 소스 파일, .obj 파일 또는 라이브러리의 이름입니다.  CL은 소스 파일을 컴파일한 다음 .obj 파일과 라이브러리를 링커에 전달합니다.  자세한 내용은 [CL 파일 이름 구문](../../build/reference/cl-filename-syntax.md)을 참조하십시오.|  
|*lib*|하나 이상의 라이브러리 이름입니다.  CL은 이 이름을 링커에 전달합니다.|  
|*command\-file*|여러 개의 옵션과 파일 이름이 들어 있는 파일입니다.  자세한 내용은 [CL 명령 파일](../../build/reference/cl-command-files.md)을 참조하십시오.|  
|*link\-opt*|하나 이상의 [링커 옵션](../../build/reference/linker-options.md)입니다.  CL은 이 옵션을 링커에 전달합니다.|  
  
 옵션, 파일 이름 및 라이브러리 이름은 명령줄의 문자 개수가 1024개를 초과하지 않는 범위 내에서 제한 없이 지정할 수 있습니다. 이러한 제한은 운영 체제에 의해 결정됩니다.  
  
 cl.exe의 반환 값에 대한 자세한 내용은 [cl.exe의 반환 값](../../build/reference/return-value-of-cl-exe.md)을 참조하십시오.  
  
> [!NOTE]
>  1024개로 제한된 명령줄 입력 문자 제한은 다음 Windows 버전에서 달라질 수 있습니다.  
  
## 참고 항목  
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)