---
title: "문을 레이블이 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- labeled statement
- statements, labeled
ms.assetid: 456a26d5-0fcc-4d1a-b71f-fa9ff3d73b91
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 139b94ab0287de5449e0b03ca96f5443049cfb5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="labeled-statements"></a>레이블 문
레이블은 프로그램 제어를 지정된 문에 직접 전송하는 데 사용됩니다.  
  
```  
identifier :  statement  
case constant-expression :  statement  
default :  statement  
```  
  
 레이블의 범위는 레이블이 선언된 함수 전체입니다.  
  
## <a name="remarks"></a>설명  
 세 가지 형식의 레이블 문이 있습니다. 모두 문에서 특정 형식의 레이블을 분리하는 데 콜론을 사용합니다. case 및 기본 레이블은 case 문과 관련이 있습니다.  
  
```cpp  
#include <iostream>   
using namespace std;   
  
void test_label(int x) {  
  
    if (x == 1){  
        goto label1;  
    }  
    goto label2;  
  
label1:  
    cout << "in label1" << endl;  
    return;  
  
label2:  
    cout << "in label2" << endl;  
    return;  
}  
  
int main() {  
    test_label(1);  // in label1   
    test_label(2);  // in label2  
}  
  
```  
  
 **Goto 문**  
  
 모양을 *식별자* 소스 프로그램에 레이블이 나타나면 레이블이 선언 합니다. 만 [goto](../cpp/goto-statement-cpp.md) 문을 컨트롤을 전송할 수 있습니다는 *식별자* 레이블. 다음 코드 조각 사용을 보여 줍니다.는 `goto` 문 및 *식별자* 레이블:  
  
 레이블은 단독으로 나타날 수 없고 항상 문에 첨부되어야 합니다. 레이블이 단독으로 필요한 경우 레이블 뒤에 null 문을 배치하세요.  
  
 레이블에는 함수 범위가 있으며 함수 내에서 레이블을 다시 선언할 수 없습니다. 그러나 다른 함수에서 동일한 이름을 레이블로 사용할 수 있습니다.  
  
```  
// labels_with_goto.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   using namespace std;  
   goto Test2;  
  
   cout << "testing" << endl;  
  
   Test2:  
      cerr << "At Test2 label." << endl;  
}  
  
//Output: At Test2 label.  
```  
  
 **Case 문**  
  
 다음에 표시 되는 레이블을 **대/소문자** 키워드 외부에 나타날 수 없습니다는 `switch` 문. (이러한 제한에도 적용 됩니다는 **기본** 키워드입니다.) 다음 코드에서는 올바른 사용을 보여 줍니다. **대/소문자** 레이블:  
  
```  
// Sample Microsoft Windows message processing loop.  
switch( msg )  
{  
   case WM_TIMER:    // Process timer event.  
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );  
      ShowWindow( hWnd, SW_SHOWNA );  
      nIcon %= 14;  
      Yield();  
      break;  
  
   case WM_PAINT:  
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );  
      hDC = BeginPaint( hWnd, &ps );   
      EndPaint( hWnd, &ps );  
      break;  
  
   default:  
      // This choice is taken for all messages not specifically  
      //  covered by a case statement.  
  
      return DefWindowProc( hWnd, Message, wParam, lParam );  
      break;  
}  
```  
  
## <a name="labels-in-the-case-statement"></a>case 문의 레이블  
 다음에 표시 되는 레이블을 **대/소문자** 키워드 외부에 나타날 수 없습니다는 `switch` 문. (이러한 제한에도 적용 됩니다는 **기본** 키워드입니다.) 다음 코드에서는 올바른 사용을 보여 줍니다. **대/소문자** 레이블:  
  
```  
// Sample Microsoft Windows message processing loop.  
switch( msg )  
{  
   case WM_TIMER:    // Process timer event.  
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );  
      ShowWindow( hWnd, SW_SHOWNA );  
      nIcon %= 14;  
      Yield();  
      break;  
  
   case WM_PAINT:  
      // Obtain a handle to the device context.  
      // BeginPaint will send WM_ERASEBKGND if appropriate.  
  
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );  
      hDC = BeginPaint( hWnd, &ps );  
  
      // Inform Windows that painting is complete.  
  
      EndPaint( hWnd, &ps );  
      break;  
  
   case WM_CLOSE:  
      // Close this window and all child windows.  
  
      KillTimer( hWnd, TIMER1 );  
      DestroyWindow( hWnd );  
      if ( hWnd == hWndMain )  
         PostQuitMessage( 0 );  // Quit the application.  
      break;  
  
   default:  
      // This choice is taken for all messages not specifically  
      //  covered by a case statement.  
  
      return DefWindowProc( hWnd, Message, wParam, lParam );  
      break;  
}  
```  
  
## <a name="labels-in-the-goto-statement"></a>goto 문의 레이블  
 모양을 *식별자* 소스 프로그램에 레이블이 나타나면 레이블이 선언 합니다. 만 [goto](../cpp/goto-statement-cpp.md) 문을 컨트롤을 전송할 수 있습니다는 *식별자* 레이블. 다음 코드 조각 사용을 보여 줍니다.는 `goto` 문 및 *식별자* 레이블:  
  
 레이블은 단독으로 나타날 수 없고 항상 문에 첨부되어야 합니다. 레이블이 단독으로 필요한 경우 레이블 뒤에 null 문을 배치하세요.  
  
 레이블에는 함수 범위가 있으며 함수 내에서 레이블을 다시 선언할 수 없습니다. 그러나 다른 함수에서 동일한 이름을 레이블로 사용할 수 있습니다.  
  
```  
// labels_with_goto.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   using namespace std;  
   goto Test2;  
  
   cout << "testing" << endl;  
  
   Test2:  
      cerr << "At Test2 label." << endl;  
// At Test2 label.  
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [C + + 문 개요](../cpp/overview-of-cpp-statements.md)   
 [switch 문(C++)](../cpp/switch-statement-cpp.md)