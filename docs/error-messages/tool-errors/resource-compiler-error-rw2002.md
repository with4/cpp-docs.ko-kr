---
title: "리소스 컴파일러 오류 RW2002 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RW2002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW2002"
ms.assetid: b1d1a49b-b50b-4b0b-9f09-c7762e2dbe8f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 리소스 컴파일러 오류 RW2002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구문 분석 오류  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  **액셀러레이터 키 형식이 있어야 합니다\(ASCII 또는 VIRTKEY\).**  
  
     **ACCELERATORS** 문의 `type` 필드에는ASCII 또는 VIRTKEY 값 중 하나가 포함되어야 합니다.  
  
2.  **액셀러레이터 키 테이블에는 BEGIN이 있어야 합니다.**  
  
     **BEGIN** 키워드는 **ACCELERATORS** 키워드 바로 뒤에 와야 합니다.  
  
3.  **대화 상자에는 BEGIN이 있어야 합니다.**  
  
     **BEGIN** 키워드는 **DIALOG** 키워드 바로 뒤에 와야 합니다.  
  
4.  **메뉴에는 BEGIN이 있어야 합니다.**  
  
     **BEGIN** 키워드는 **MENU** 키워드 바로 뒤에 와야 합니다.  
  
5.  **RCData에는 BEGIN이 있어야 합니다.**  
  
     **BEGIN** 키워드는 **RCDATA** 키워드 바로 뒤에 와야 합니다.  
  
6.  **문자열 테이블에는 BEGIN이 있어야 합니다.**  
  
     **BEGIN** 키워드는 **STRINGTABLE** 키워드 바로 뒤에 와야 합니다.  
  
7.  **문자열 상수를 다시 사용할 수 없습니다.**  
  
     **STRINGTABLE** 문에서 같은 값을 두 번 사용했습니다.  중복되는 10진수 값과 16진수 값을 함께 사용하지 않아야 합니다.  **STRINGTABLE**의 각 ID는 고유해야 합니다.  최고의 효율성을 위하여 16의 배수로 시작하는 연속적인 상수를 사용하십시오.  
  
8.  **제어 문자가 범위\[^A \- ^Z\]를 벗어났습니다.**  
  
     **ACCELERATORS** 문의 제어 문자가 잘못되었습니다.  캐럿\(**^**\) 뒤에 오는 문자는 A와 Z 사이의 문자\(A와 Z 포함\)여야 합니다.  
  
9. **빈 메뉴는 사용할 수 없습니다.**  
  
     **MENU** 문에서 메뉴 항목이 정의되기 전에 **END** 키워드가 있습니다.  리소스 컴파일러에는 빈 메뉴를 사용할 수 없습니다.  **MENU** 문 안에 여는 따옴표가 없는지 확인하십시오.  
  
10. **대화 상자에는 END가 있어야 합니다.**  
  
     **END** 키워드는 **DIALOG** 문 끝에 와야 합니다.  이전 문의 여는 따옴표가 남아 있으면 안 됩니다.  
  
11. **메뉴에는 END가 있어야 합니다.**  
  
     **END** 키워드는 **MENU** 문 끝에 와야 합니다.  여는 따옴표나 일치하지 않는 **BEGIN** 및 **END** 문 쌍은 없는지 확인하십시오.  
  
12. **액셀러레이터 키 테이블에는 쉼표가 있어야 합니다.**  
  
     리소스 컴파일러를 사용할 때에는 **ACCELERATORS** 문의 `event` 및 *idvalue* 필드 사이에 쉼표가 있어야 합니다.  
  
13. **컨트롤 클래스 이름이 있어야 합니다.**  
  
     **DIALOG** 문에서 **CONTROL** 문의 `class` 필드는 BUTTON, COMBOBOX, EDIT, LISTBOX, SCROLLBAR, STATIC 또는 사용자 정의 형식 중 하나여야 합니다.  클래스를 제대로 입력했는지 확인하십시오.  
  
14. **글꼴 이름이 있어야 합니다.**  
  
     **DIALOG** 문에서 FONT 옵션의 *typeface* 필드에는 큰따옴표로 묶은 ASCII 문자열이 있어야 합니다.  이 필드는 글꼴의 이름을 지정합니다.  
  
15. **menuitem에는 ID 값이 있어야 합니다.**  
  
     **MENU** 문은 메뉴 리소스를 식별하는 이름이나 번호를 지정하는 *menuID* 필드를 포함해야 합니다.  
  
16. **메뉴 문자열이 있어야 합니다.**  
  
     각 **MENUITEM** 문과 **POPUP** 문에는 *text* 필드가 들어 있어야 합니다. 이 text 필드는 메뉴 항목이나 팝업 메뉴의 이름을 지정하는 문자열이며 큰따옴표로 묶여 있습니다.  **MENUITEM SEPARATOR** 문에는 따옴표로 묶은 문자열이 필요하지 않습니다.  
  
17. **숫자 명령 값이 있어야 합니다.**  
  
     리소스 컴파일러는 **ACCELERATORS** 문에 숫자 *idvalue* 필드를 필요로 합니다.  `#define` 상수를 사용하여 값을 지정하고 상수를 제대로 입력했는지 확인하십시오.  
  
18. **문자열 테이블에는 숫자 상수가 있어야 합니다.**  
  
     `#define` 문에 정의된 숫자 상수는 **STRINGTABLE** 문에서 **BEGIN** 키워드 바로 뒤에 와야 합니다.  
  
19. **숫자 크기가 있어야 합니다.**  
  
     **DIALOG** 문에서 FONT 옵션의 pointsize 필드에는 정수 크기 값이 있어야 합니다.  
  
20. **숫자 대화 상자 상수가 있어야 합니다.**  
  
     **DIALOG** 문에는 *x, y, width* 및 *height* 필드에 정수 값이 있어야 합니다.  이 값이 **DIALOG** 키워드 뒤에 포함되어 있으며 음수가 아닌지 확인하십시오.  
  
21. **STRINGTABLE에는 문자열이 있어야 합니다.**  
  
     **STRINGTABLE** 문의 각 stringid 값 뒤에는 문자열이 있어야 합니다.  
  
22. **문자열 또는 상수 액셀러레이터 키 명령이 있어야 합니다.**  
  
     리소스 컴파일러는 액셀러레이터 키에 대해 어떤 종류의 키가 설정되어 있는지 확인할 수 없습니다.  **ACCELERATORS** 문의 `event` 필드가 잘못되었을 수 있습니다.  
  
23. **ID에는 숫자가 있어야 합니다.**  
  
     **DIALOG** 문에서 컨트롤 문의 `id` 필드에는 숫자가 있어야 합니다.  컨트롤 ID에 숫자나 `#define` 문을 사용했는지 확인하십시오.  
  
24. **대화 상자 클래스에는 따옴표가 붙은 문자열이 있어야 합니다.**  
  
     **DIALOG** 문에서 CLASS 옵션의 `class` 필드에는 큰따옴표로 묶은 정수나 문자열이 있어야 합니다.  
  
25. **대화 상자 제목에는 따옴표가 붙은 문자열이 있어야 합니다.**  
  
     **DIALOG** 문에서 CAPTION 옵션의 `captiontext` 필드에는 큰따옴표로 묶은 ASCII 문자열이 있어야 합니다.  
  
26. **파일을 찾을 수 없습니다: filename**  
  
     리소스 컴파일러 명령줄에서 지정한 파일이 없습니다.  파일이 다른 디렉터리로 이동되었는지와 파일 이름이나 경로를 올바르게 입력했는지 확인하십시오.  가능한 경우 파일은 **INCLUDE** 환경 변수나 Visual Workbench 설정을 사용하여 검색됩니다.  
  
27. **글꼴 이름은 서수여야 합니다.**  
  
     FONT 문의 pointsize 필드에는 문자열이 아닌 정수가 있어야 합니다.  
  
28. **액셀러레이터 키가 잘못되었습니다.**  
  
     **ACCELERATORS** 문의 `event` 필드가 인식되지 않거나 길이가 두 자를 초과합니다.  
  
29. **액셀러레이터 키 형식이 잘못되었습니다\(ASCII 또는 VIRTKEY\).**  
  
     **ACCELERATORS** 문의 `type` 필드에는ASCII 또는 VIRTKEY 값 중 하나가 포함되어야 합니다.  
  
30. **제어 문자가 잘못되었습니다.**  
  
     **ACCELERATORS** 문의 제어 문자가 잘못되었습니다.  올바른 제어 문자는 캐럿\(^\) 뒤에 한 글자만 붙습니다.  
  
31. **컨트롤 형식이 잘못되었습니다.**  
  
     **DIALOG** 문의 각 컨트롤 문은 CHECKBOX, COMBOBOX, CONTROL, CTEXT, DEFPUSHBUTTON, EDITTEXT, GROUPBOX, ICON, LISTBOX, LTEXT, PUSHBUTTON, RADIOBUTTON, RTEXT, SCROLLBAR 중 하나여야 합니다.  컨트롤 문을 제대로 입력했는지 확인하십시오.  
  
32. **형식이 잘못되었습니다.**  
  
     리소스 형식이 WINDOWS.h 파일에 정의되지 않은 형식입니다.  
  
33. **컨트롤에는 텍스트 문자열이나 서수가 있어야 합니다.**  
  
     **DIALOG** 문에서 **CONTROL** 문의 text 필드는 텍스트 문자열이거나 컨트롤 형식에 대한 서수 참조여야 합니다.  서수를 사용하는 경우 해당 컨트롤에 대한 `#define` 문이 있는지 확인하십시오.  
  
34. **괄호 짝이 일치하지 않습니다.**  
  
     **DIALOG** 문에서 모든 여는 괄호를 닫았는지 확인하십시오.  
  
35. **RCData에 예기치 않은 값이 있습니다.**  
  
     **RCDATA** 문의 raw\-data 값은 각각 쉼표로 분리된 정수 또는 문자열이어야 합니다.  쉼표 또는 문자열 주위의 따옴표를 제거하지 않았는지 확인하십시오.  
  
36. **알 수 없는 메뉴 하위 형식입니다.**  
  
     **MENU** 문의 *item\-definition* 필드에는 **MENUITEM** 및 **POPUP** 문만 있어야 합니다.