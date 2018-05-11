---
title: 링커 도구 오류 LNK1200 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1200
dev_langs:
- C++
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab32939c55dce5e27f907f3d23e639b24741cdc3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1200"></a>링커 도구 오류 LNK1200
'filename' 프로그램 데이터베이스를 읽는 동안 오류가 발생  
  
 프로그램 데이터베이스 (PDB)를 읽을 수 없습니다.  
  
 이 오류는 파일 손상으로 발생할 수 있습니다.  
  
 경우 `filename` PDB는 개체 파일을 사용 하 여 개체 파일을 recompile [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)합니다.  
  
 경우 `filename` PDB 및 다시 연결을 삭제, 기본 출력 파일에 대 한 PDB 이며 증분 링크 하는 동안이 오류가 발생 했습니다.