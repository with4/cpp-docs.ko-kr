---
title: "링커 도구 경고 LNK4070 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4070
dev_langs: C++
helpviewer_keywords: LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c3c683593b9019851b1a330a613adcf7a18c4a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4070"></a>링커 도구 경고 LNK4070
/OUT:filename 지시문입니다. 출력 파일 이름 'filename';에서 다른 EXP 지시문을 무시합니다.  
  
 `filename` 에 지정 된 된 [이름](../../build/reference/name-c-cpp.md) 또는 [라이브러리](../../build/reference/library.md) .exp 파일을 만들 때 문 출력에 따라 달라 집니다 `filename` 기본적으로 사용 하거나는 를지정된하는[/Out](../../build/reference/out-output-file-name.md) 옵션입니다.  
  
 개발 환경에서 및 프로젝트의.def 파일이 업데이트 되지 않은 출력 파일의 이름을 변경 하면이 경고가 표시 됩니다. 이 경고를 해결 하려면.def 파일을 수동으로 업데이트 합니다.  
  
 결과 DLL을 사용 하는 클라이언트 프로그램에 문제가 발생할 수 있습니다.