---
title: 링커 도구 오류 LNK2027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2027
dev_langs:
- C++
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 156310a0d21651b9fd2ee6002ace419db4996681
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2027"></a>링커 도구 오류 LNK2027
확인 되지 않은 모듈 참조 ' module'  
  
 링커로 전달 하는 파일에도 지정 된 모듈에 대 한 종속성 **/ASSEMBLYMODULE** 링커 직접 전달 합니다.  
  
 LNK2027를 해결 하려면 다음 중 하나를 수행 합니다.  
  
-   전달 하지 마십시오 링커에 모듈 종속성을 가진 파일.  
  
-   사용 하 여 모듈 지정 **/ASSEMBLYMODULE**합니다.  
  
-   모듈이 안전한 .netmodule인 경우 모듈을 링커에 직접 전달합니다.  
  
 자세한 내용은 참조 [/ASSEMBLYMODULE (MSIL 모듈을 어셈블리에 추가)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) 및 [링커 입력 파일로.netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)합니다.