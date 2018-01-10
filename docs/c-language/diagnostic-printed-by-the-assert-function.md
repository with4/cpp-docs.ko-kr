---
title: "assert 함수에서 진단 인쇄 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 243956f1d85b07b5d5b810ebfd112b2cbfe16242
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert 함수에서 진단 인쇄
**ANSI 4.2** **assert** 함수에 의해 인쇄되는 진단 및 해당 함수의 종료 동작  
  
 **assert** 함수는 진단 메시지를 인쇄하고 식이 false(0)이면 **abort** 루틴을 호출합니다. 진단 메시지의 형식은 다음과 같습니다.  
  
 **Assertion failed**: *expression***, file** *filename***, line** *linenumber*  
  
 여기서 filename은 소스 파일의 이름이며 linenumber는 소스 파일에서 실패한 어설션의 줄 번호입니다. 식이 true(0이 아님)이면 어떤 작업도 수행되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [라이브러리 함수](../c-language/library-functions.md)