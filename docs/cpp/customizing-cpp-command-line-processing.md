---
title: C + + 명령줄 처리 사용자 지정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _setenvp
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- command line [C++], processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line [C++], processing arguments
- suppressing environment processing
- _setenvp function
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9415073630505e3cc879f53de14ed469c7e0e2ba
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939054"
---
# <a name="customizing-c-command-line-processing"></a>C++ 명령줄 처리 사용자 지정
## <a name="microsoft-specific"></a>Microsoft 전용  
 프로그램에서 명령줄 인수를 사용하지 않는 경우 명령줄 처리를 수행하는 라이브러리 루틴의 사용을 억제하여 약간의 공간을 절약할 수 있습니다. 이 루틴 `_setargv` 에 대 한 설명은 [와일드 카드 확장](../cpp/wildcard-expansion.md)합니다. 용도 표시 하지 않으려면 포함 하는 파일에서 아무 작업도 수행 하지 않는 루틴을 정의 합니다 `main` 작동 하 고 이름을 `_setargv`입니다. 에 대 한 호출 `_setargv` 의 정의로 충족 한 후 `_setargv`, 되며 라이브러리 버전이 로드 되지 않습니다.  
  
 마찬가지로, 통해 환경 테이블에 액세스 하지 않을 경우 합니다 `envp` 인수를 대신 사용할 사용자 고유의 빈 루틴을 제공할 수 있습니다 `_setenvp`, 환경 처리 루틴입니다. 와 마찬가지로 합니다 `_setargv` 함수를 `_setenvp` 으로 선언 해야 **extern "C"** 합니다.  
  
 프로그램에 대 한 호출을 수행할 수는 `spawn` 또는 `exec` C 런타임 라이브러리 루틴의 제품군입니다. 이런 경우에는 부모 프로세스에서 자식 프로세스로 환경을 전달하는 데 이 루틴이 사용되므로 환경 처리 루틴을 억제하면 안 됩니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [main: 프로그램 시작](../cpp/main-program-startup.md)