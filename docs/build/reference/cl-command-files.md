---
title: "CL 명령 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, command files
- command files
- command files, CL compiler
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a711b2f4a484a6370af828c5d0aad522686ca3f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cl-command-files"></a>CL 명령 파일
명령 파일은 옵션과에 입력 하지 않으면 파일 이름이 포함 된 텍스트 파일의 [명령줄](../../build/reference/compiler-command-line-syntax.md) 사용 하 여 지정 하거나는 [CL 환경 변수](../../build/reference/cl-environment-variables.md)합니다. Cl 컴파일러 명령 파일을 CL 환경 변수에서 또는 명령줄에서를 인수로 사용 합니다. 명령줄이나 CL 환경 변수와는 달리 명령 파일을 사용하면 여러 줄로 구성된 옵션과 파일 이름을 사용할 수 있습니다.  
  
 옵션 및 명령 파일의 파일 이름을 CL 환경 변수 내에서 또는 명령줄에서 명령 파일의 위치에 따라 처리 됩니다. 그러나 /link 옵션에에서 나타나는 경우 명령 파일, 줄의 나머지 부분에 있는 모든 옵션을 링커에 전달 됩니다. 명령 파일의 다음 줄의 옵션 및 명령 파일 호출 다음 명령줄 옵션은 여전히 컴파일러 옵션으로 사용할 수 있습니다. 옵션의 순서 해석에 미치는 영향에 대 한 자세한 내용은 참조 하십시오. [CL 옵션 순서](../../build/reference/order-of-cl-options.md)합니다.  
  
 명령 파일 CL 명령을 사용할 수 없습니다. 각 옵션 시작 하 고 끝나야 하며 같은 줄에서 백슬래시를 사용할 수 없습니다 (\\)을 두 줄 옵션을 결합 합니다.  
  
 명령 파일을 지정 하 여는 at 기호 (@) 뒤에 파일 이름이; 파일 이름이 절대 또는 상대 경로 지정할 수 있습니다.  
  
 예를 들어, 다음 명령은 라는 응답 파일  
  
```  
/Og /link LIBC.LIB  
```  
  
 다음 CL 명령을 지정 하십시오.  
  
```  
CL /Ob2 @RESP MYAPP.C  
```  
  
 CL 명령을 다음과 같습니다.  
  
```  
CL /Ob2 /Og MYAPP.C /link LIBC.LIB  
```  
  
 Note는 명령 파일 명령과 명령줄 효과적으로 결합 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)