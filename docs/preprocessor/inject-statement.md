---
title: inject_statement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7dacc2867b767495c608789b9efbe23bf7aa7110
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="injectstatement"></a>inject_statement
**C + + 전용**  
  
 소스 텍스트로서 인수를 형식 라이브러리 헤더에 삽입합니다.  
  
## <a name="syntax"></a>구문  
  
```  
inject_statement("source_text")  
```  
  
#### <a name="parameters"></a>매개 변수  
 `source_text`  
 형식 라이브러리 헤더 파일에 삽입되는 소스 텍스트입니다.  
  
## <a name="remarks"></a>설명  
 헤더 파일의 형식 라이브러리 내용을 래핑하는 네임스페이스 선언의 시작 부분에 텍스트가 배치됩니다.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)