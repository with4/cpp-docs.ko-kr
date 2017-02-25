---
title: "프롤로그/에필로그 코드를 작성할 때 고려 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__LOCAL_SIZE 상수"
  - "에필로그 코드"
  - "프롤로그 코드"
  - "스택 프레임 레이아웃"
  - "스택, 스택 프레임 레이아웃"
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 프롤로그/에필로그 코드를 작성할 때 고려 사항
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 자신의 prolog 및 epilog 코드 시퀀스를 작성하기 전에 스택 프레임을 배치하는 방법을 이해하는 것이 중요합니다.  **\_\_LOCAL\_SIZE** 기호를 사용하는 방법을 알아두는 것도 좋습니다.  
  
##  <a name="_pluslang_c.2b2b_.stack_frame_layout"></a> 스택 프레임 레이아웃  
 이 예제에서는 32비트 함수에 표시될 수 있는 표준 prolog 코드를 보여 줍니다.  
  
```  
push        ebp                ; Save ebp  
mov         ebp, esp           ; Set stack frame pointer  
sub         esp, localbytes    ; Allocate space for locals  
push        <registers>        ; Save registers  
```  
  
 `localbytes` 변수는 지역 변수를 위해 스택에 필요한 바이트 수를 나타내고, `<registers>` 변수는 스택에 저장될 레지스터의 목록을 나타내는 자리 표시자입니다.  레지스터를 푸시한 후 스택에 다른 적절한 데이터를 배치할 수 있습니다.  다음은 해당 epilog 코드입니다.  
  
```  
pop         <registers>   ; Restore registers  
mov         esp, ebp      ; Restore stack pointer  
pop         ebp           ; Restore ebp  
ret                       ; Return from function  
```  
  
 스택은 항상 높은 메모리 주소에서 낮은 메모리 주소로 감소합니다.  기본 포인터\(`ebp`\)는 `ebp`의 푸시된 값을 가리킵니다.  지역 변수 영역은 `ebp-4`에서 시작합니다.  지역 변수에 액세스하려면 `ebp`에서 적절한 값을 빼는 방법으로 `ebp`에서 오프셋을 계산합니다.  
  
##  <a name="_pluslang___local_size"></a> \_\_LOCAL\_SIZE  
 컴파일러는 함수 프롤로그 코드의 인라인 어셈블러 블록에서 사용할 **\_\_LOCAL\_SIZE** 기호를 제공합니다.  이 기호는 사용자 지정 프롤로그 코드에서 스택 프레임에 지역 변수를 위한 공간을 할당하는 데 사용됩니다.  
  
 컴파일러는 **\_\_LOCAL\_SIZE**의 값을 결정합니다.  이 값은 모든 사용자 정의 지역 변수와 컴파일러에서 생성된 임시 변수의 총 바이트 수입니다.  **\_\_LOCAL\_SIZE**는 즉시 피연산자로만 사용할 수 있으며 식에서는 사용할 수 없습니다.  이 기호의 값을 변경하거나 다시 정의하면 안 됩니다.  예를 들면 다음과 같습니다.  
  
```  
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay  
mov        eax, [ebp - __LOCAL_SIZE]   ;Error  
```  
  
 사용자 지정 프롤로그 및 에필로그 시퀀스를 포함하는 naked 함수의 다음 예제에서는 프롤로그 시퀀스에서 **\_\_LOCAL\_SIZE** 기호를 사용합니다.  
  
```  
// the__local_size_symbol.cpp  
// processor: x86  
__declspec ( naked ) int main() {  
   int i;  
   int j;  
  
   __asm {      /* prolog */  
      push   ebp  
      mov      ebp, esp  
      sub      esp, __LOCAL_SIZE  
      }  
  
   /* Function body */  
   __asm {   /* epilog */  
      mov      esp, ebp  
      pop      ebp  
      ret  
      }  
}  
```  
  
### Microsoft 전용 종료  
  
## 참고 항목  
 [Naked 함수 호출](../cpp/naked-function-calls.md)