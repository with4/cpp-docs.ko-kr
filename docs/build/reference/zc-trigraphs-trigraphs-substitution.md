---
title: "-Zc: trigraphs (삼중 자 대체) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Zc
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 739e772c87c937a552e07a32fa5bb80b1a1e2508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs(삼중자 대체)
때 **/zc: trigraphs** 지정, 컴파일러가 해당 문장 부호 문자를 사용 하 여 삼중 자는 문자 시퀀스를 바꿉니다. 삼중 자 대체를 해제 하려면 지정 **/Zc:trigraphs-**합니다. 기본적으로 **/zc: trigraphs** 꺼져 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Zc:trigraphs[-]  
```  
  
## <a name="remarks"></a>설명  
 삼중자는 두 개의 연속 물음표("??")와 고유한 세 번째 문자로 구성됩니다. 예를 들어, 컴파일러 대체는 "?? = "'#' 문자를 사용 하 여 삼중 자입니다. 삼중자는 특정 문장 부호 문자에 대한 편리한 그래픽 표현을 포함하지 않는 문자 집합이 사용되는 C 소스 파일에서 사용합니다.  
  
 C/c + + 삼중 자 및 삼중 자를 사용 하는 방법을 보여 주는 예제 목록 참조 [삼중 자](../../c-language/trigraphs.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [/Zc (규칙)](../../build/reference/zc-conformance.md)   
 [삼중자](../../c-language/trigraphs.md)