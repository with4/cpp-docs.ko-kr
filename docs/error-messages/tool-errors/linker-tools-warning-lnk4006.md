---
title: 링커 도구 경고 LNK4006 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4006
dev_langs:
- C++
helpviewer_keywords:
- LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 261d5dcc27c44291ddc6de4a6440cde040a84ed7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302557"
---
# <a name="linker-tools-warning-lnk4006"></a>링커 도구 경고 LNK4006
개체에 이미 정의 된 기호 두 번째 정의가 무시 됩니다.  
  
 데코레이팅된 폼으로 표시되는 해당 `symbol` 기호는 여러 번 정의되었습니다. 이 경고가 발생할 경우 `symbol` 을 두 번 추가 되지만 첫 번째 형태에만 사용 됩니다.  
  
 두 개의 가져오기 라이브러리를 하나로 병합 하려는 경우이 경고를 가져올 수 있습니다.  
  
 C 런타임 라이브러리를 다시 작성 하는 경우이 메시지를 무시할 수 있습니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  주어진 `symbol` 로 만든 패키지 함수 수 [/Gy](../../build/reference/gy-enable-function-level-linking.md)합니다. 이 기호는 둘 이상의 파일에 포함 되어 있지만 컴파일 간에 변경 되었습니다. 포함 된 모든 파일을 다시 컴파일하는 `symbol`합니다.  
  
2.  지정 된 `symbol` 수 다르게 정의 되어 서로 다른 라이브러리에 있는 두 멤버 개체에 있습니다.  
  
3.  절대 정의 되어 있습니다을 두 번 각 정의에서 다른 값을 사용 합니다.  
  
4.  라이브러리를 조합할 때 오류 메시지가 수신 되 면 `symbol` 에 추가 되 고 라이브러리에 이미 있습니다.