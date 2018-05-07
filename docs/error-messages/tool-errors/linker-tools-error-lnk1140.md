---
title: 링커 도구 오류 LNK1140 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1140
dev_langs:
- C++
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc0d59589a1882aca4ef2deb419e1e4f1081e52b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1140"></a>링커 도구 오류 LNK1140
프로그램 데이터베이스에 너무 많은 모듈 링크 합니다. /PDB: NONE  
  
 프로젝트는 4096 개 이상의 모듈을 포함합니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  사용 하 여 다시 연결 [/PDB: NONE](../../build/reference/pdb-use-program-database.md)합니다.  
  
2.  정보를 디버깅 하지 않고 모듈을 컴파일하십시오.  
  
3.  모듈의 수를 줄입니다.