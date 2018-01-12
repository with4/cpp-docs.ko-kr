---
title: "컴파일러 오류 C2338 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2338
dev_langs: C++
helpviewer_keywords: C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0171654bde5b056a7e6695ea5fbbe84edb62f83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2338"></a>컴파일러 오류 C2338  
  
> *오류 메시지*  
  
이 오류를 때문일 수 있습니다는 `static_assert` 컴파일 중에 오류가 발생 합니다. 메시지에서 제공 되는 `static_assert` 매개 변수입니다.   
  
컴파일러에 외부 공급자에서이 오류 메시지를 생성할 수도 있습니다. 대부분의 경우에서 이러한 오류는 특성 공급자 ATLPROV 같은 DLL에서 보고 됩니다. 몇 가지 일반적인 형태의이 메시지는 다음과 같습니다.

> '*특성*' Atl 특성 공급자: 오류 ATL*번호* *메시지*  
  
> 특성의 사용이 잘못 '*특성*'
  
> '*사용*': '사용' 특성에 대 한 잘못 된 형식  
  
이러한 오류는 종종 복구할 하며 심각한 컴파일러 오류가 올 수 있습니다.  
  
이러한 문제를 해결 하려면 특성 사용을 수정 하십시오. 예를 들어, 경우에 따라 특성 매개 변수 선언 되어야 합니다 사용할 수 있습니다. ATL 오류 번호를 제공 하는 경우 자세한 내용은 해당 오류에 대 한 설명서를 확인 합니다.  
