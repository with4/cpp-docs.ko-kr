---
title: "bad_function_call 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- bad_function_call
- std::bad_function_call
- functional/std::bad_function_call
dev_langs:
- C++
helpviewer_keywords:
- bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: f293f074f2b8e2334dc70fbebba8e6f4c17efecc
ms.openlocfilehash: 89ec0f614151128decfbc2c0a451ca9f55f4e85e
ms.lasthandoff: 02/24/2017

---
# <a name="badfunctioncall-class"></a>bad_function_call 클래스
잘못된 함수 호출을 보고합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class bad_function_call  
 : public std::exception {  
 };  
```  
  
## <a name="remarks"></a>설명  
 이 클래스는 [function 클래스](../standard-library/function-class.md)에서 `operator()`에 대한 호출이 있었음을 나타내기 위해 throw된 예외를 설명합니다.

