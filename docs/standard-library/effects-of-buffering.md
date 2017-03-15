---
title: "버퍼링 효과 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: d888b6d16e0a71168e0615d89bbd1d03c51afad8
ms.lasthandoff: 02/24/2017

---
# <a name="effects-of-buffering"></a>버퍼링 효과
다음 예제에서는 버퍼링 효과 보여 줍니다. 프로그램에서 `please wait`를 인쇄하고 5초 기다린 후 계속하도록 할 수 있습니다. 그러나 출력이 버퍼링되기 때문에 반드시 이런 방식으로 작동하지는 않습니다.  
  
```  
// effects_buffering.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <time.h>  
using namespace std;  
  
int main( )  
{  
   time_t tm = time( NULL ) + 5;  
   cout << "Please wait...";  
   while ( time( NULL ) < tm )  
      ;  
   cout << "\nAll done" << endl;  
}  
```  
  
 프로그램이 논리적으로 작동하도록 하려면 메시지가 표시될 때 `cout` 개체 자체가 비어 있어야 합니다. `ostream` 개체를 플러시하려면 `flush` 조작자로 보냅니다.  
  
```  
cout <<"Please wait..." <<flush;  
```  
  
 이 단계에서는 버퍼를 플러시하여 메시지가 인쇄된 후 대기하도록 합니다. 또한 버퍼를 플러시하고 캐리지 리턴을 출력하는 `endl` 조작자를 사용하거나, `cin` 개체를 사용할 수 있습니다. 이 개체는 `cerr` 또는 `clog` 개체와 함께 일반적으로 `cout` 개체에 연결됩니다. 따라서 `cin` , `cerr` 또는 `clog` 개체를 사용하면 `cout` 개체가 플러시됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [출력 스트림](../standard-library/output-streams.md)


