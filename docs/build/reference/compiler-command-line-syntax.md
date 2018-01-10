---
title: "컴파일러 명령줄 구문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7fb89aca1990d44d7ef62ea76788b38e8ffa1d6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-command-line-syntax"></a>컴파일러 명령줄 구문
CL 명령줄에 다음 구문을 사용합니다.  
  
```  
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]  
```  
  
 다음 표에서 CL 명령에 대 한 입력을 설명합니다.  
  
|입력|의미|  
|-----------|-------------|  
|*옵션*|하나 이상의 [CL 옵션](../../build/reference/compiler-options.md)합니다. 모든 옵션이 모든 지정 된 소스 파일에 적용 하는 참고 합니다. 옵션은 슬래시 (/) 또는 대시 (-)으로 지정 됩니다. 옵션 및 인수 사이 공백을 허용 옵션의 설명 문서는 인수를 사용 하는 옵션입니다. /HELP 옵션) (제외 옵션 이름은 대/소문자를 구분 합니다. 참조 [CL 옵션 순서](../../build/reference/order-of-cl-options.md) 자세한 정보에 대 한 합니다.|  
|`file`|하나 이상의 소스 파일,.obj 파일 또는 라이브러리의 이름입니다. CL 소스 파일을 컴파일한.obj 파일 및 라이브러리의 이름의을 링커에 전달 합니다. 참조 [CL 파일 이름 구문](../../build/reference/cl-filename-syntax.md) 자세한 정보에 대 한 합니다.|  
|*lib*|하나 이상의 라이브러리 이름입니다. CL 이러한 이름을 링커에 전달합니다.|  
|*명령 파일*|여러 개의 옵션 및 파일 이름을 포함 하는 파일입니다. 참조 [CL 명령 파일](../../build/reference/cl-command-files.md) 자세한 정보에 대 한 합니다.|  
|*링크 선택*|하나 이상의 [링커 옵션](../../build/reference/linker-options.md)합니다. CL 이러한 옵션을 링커에 전달합니다.|  
  
 명령줄에는 문자 수는 1024, 운영 체제에서 범위 내에서 제한 초과 하지 않는 상태로 임의 개수의 옵션, 파일 이름 및 라이브러리 이름을 지정할 수 있습니다.  
  
 Cl.exe의 반환 값에 대 한 정보를 참조 하십시오. [cl.exe의 반환 값](../../build/reference/return-value-of-cl-exe.md) 합니다.  
  
> [!NOTE]
>  이후 버전의 Windows에서 동일 하 게 유지 하는 1024 자 명령줄 입력된 제한 보장 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)