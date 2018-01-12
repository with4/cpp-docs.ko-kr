---
title: "링커 도구 오류 LNK1140 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1140
dev_langs: C++
helpviewer_keywords: LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a5a7bce157359d547f91ba2b560cf258e231b4a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1140"></a>링커 도구 오류 LNK1140
프로그램 데이터베이스에 너무 많은 모듈 링크 합니다. /PDB: NONE  
  
 프로젝트는 4096 개 이상의 모듈을 포함합니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  사용 하 여 다시 연결 [/PDB: NONE](../../build/reference/pdb-use-program-database.md)합니다.  
  
2.  정보를 디버깅 하지 않고 모듈을 컴파일하십시오.  
  
3.  모듈의 수를 줄입니다.