---
title: C Pragmas | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- pragmas, C/C++
ms.assetid: 3d6d36b4-d565-4632-a4cd-e39aeaded5ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a87a6518eec495961d1f8d40c625e589db01bd3b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382116"
---
# <a name="c-pragmas"></a>C Pragma

**Microsoft 전용**

*pragma*는 컴파일러가 컴파일 타임에 특정 작업을 수행하도록 지시합니다. Pragma는 컴파일러마다 서로 다릅니다. 예를 들어 **optimize** pragma를 사용하여 프로그램에서 수행하는 최적화를 설정할 수 있습니다. Microsoft C pragma는 다음과 같습니다.

|||||
|-|-|-|-|
|**alloc_text**|**data_seg**|**inline_recursion**|**setlocale**|
|**auto_inline**|**function**|**intrinsic**|**warning**|
|**check_stack**|**hdrstop**|**message**||
|**code_seg**|**include_alias**|**optimize**||
|**comment**|**inline_depth**|**pack**||

Microsoft C 컴파일러 pragmas에 대한 설명은 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)를 참조하세요.

 **Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[원본 파일 및 원본 프로그램](../c-language/source-files-and-source-programs.md)  
