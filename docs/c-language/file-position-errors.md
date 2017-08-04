---
title: "파일 위치 오류 | Microsoft Docs"
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
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
caps.latest.revision: 6
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
ms.openlocfilehash: f81176b3b92b7ab92954947bb98e3bd14b93a290
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="file-position-errors"></a>파일 위치 오류
**ANSI 4.9.9.1, 4.9.9.4** 실패 시 `errno` 매크로가 `fgetpos` 또는 `ftell` 함수를 통해 설정되는 값  
  
 `fgetpos` 또는 `ftell`이 실패할 때 `errno`는 위치가 유효하지 않은 경우 매니페스트 상수 `EINVAL`로 설정되고 파일 번호가 잘못된 경우 EBADF로 설정됩니다. 상수는 ERRNO.H에서 정의됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [라이브러리 함수](../c-language/library-functions.md)
