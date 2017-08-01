---
title: C Pragmas | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- pragmas, C/C++
ms.assetid: 3d6d36b4-d565-4632-a4cd-e39aeaded5ad
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: b511f6f1d7f9fab0b45f345e39e1251df520624f
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="c-pragmas"></a>C Pragma
**Microsoft 전용**  
  
 "pragma"는 컴파일러가 컴파일 타임에 특정 작업을 수행하도록 지시합니다. Pragma는 컴파일러마다 서로 다릅니다. 예를 들어 **optimize** pragma를 사용하여 프로그램에서 수행하는 최적화를 설정할 수 있습니다. Microsoft C pragma는 다음과 같습니다.  
  
|||||  
|-|-|-|-|  
|**alloc_text**|**data_seg**|**inline_recursion**|**setlocale**|  
|**auto_inline**|**function**|**intrinsic**|**warning**|  
|**check_stack**|**hdrstop**|**message**||  
|**code_seg**|**include_alias**|**optimize**||  
|**comment**|**inline_depth**|**pack**||  
  
 Microsoft C 컴파일러 pragmas에 대한 설명은 *전처리기 참조*의 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)를 참조하세요.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [원본 파일 및 원본 프로그램](../c-language/source-files-and-source-programs.md)
