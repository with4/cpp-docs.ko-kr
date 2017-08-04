---
title: "Typedef 선언 | Microsoft Docs"
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
- declarations, typedef
- typedef declarations
- types [C], declarations
ms.assetid: e92a3b82-9269-4bc6-834a-6f431ccac83e
caps.latest.revision: 7
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
ms.openlocfilehash: b830afd21fafa487c006c1a6035ffdce0bc8dd7c
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="typedef-declarations"></a>Typedef 선언
typedef 선언은 typedef를 저장소 클래스로 사용하는 선언입니다. 선언자는 새 형식이 됩니다. typedef 선언을 사용하여 C에서 이미 정의된 형식이나 사용자가 선언한 형식에 대한 보다 짧거나 의미 있는 이름을 생성할 수 있습니다. typedef 이름을 사용하면 변경될 수 있는 구현 정보를 캡슐화할 수 있습니다.  
  
 typedef 선언은 변수 또는 함수 선언과 같은 방식으로 해석되지만, 선언에 형식이 지정되었다고 가정하는 대신 식별자가 형식의 동의어가 됩니다.  
  
## <a name="syntax"></a>구문  
 `declaration`:  
 *declaration-specifiers init-declarator-list* opt**;**  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *storage-class-specifier*:  
 `typedef`  
  
 *type-specifier*:  
 **void**  
  
 **char**  
  
 **short**  
  
 **int**  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **signed**  
  
 **unsigned**  
  
 *struct-or-union-specifier*  
  
 *enum-specifier*  
  
 *typedef-name*  
  
 *typedef-name*:  
 *identifier*  
  
 typedef 선언은 형식을 만드는 것이 아니라 기존 형식의 동의어나 다른 방식으로 지정할 수 있는 형식의 이름을 만듭니다. typedef 이름을 형식 지정자로 사용하는 경우 특정 형식 지정자와 함께 사용할 수 있습니다. 허용되는 한정자에는 **const** 및 `volatile`이 포함됩니다.  
  
 typedef 이름은 일반 식별자와 네임스페이스를 공유합니다(자세한 내용은 [네임스페이스](../c-language/name-spaces.md) 참조). 따라서 프로그램에 동일한 이름의 typedef 이름과 로컬 범위 식별자가 있을 수 있습니다. 예:  
  
```  
typedef char FlagType;  
  
int main()  
{  
}  
  
int myproc( int )  
{  
    int FlagType;  
}  
```  
  
 typedef와 동일한 이름의 로컬 범위 식별자를 선언하거나 같은 범위 또는 내부 범위에서 구조체 또는 공용 구조체의 멤버를 선언할 때 반드시 형식 지정자를 지정해야 합니다. 이 예제에서는 이 제약 조건을 보여 줍니다.  
  
```  
typedef char FlagType;  
const FlagType x;  
```  
  
 식별자, 구조체 멤버 또는 공용 구조체 멤버에 `FlagType` 이름을 다시 사용하려면 형식을 제공해야 합니다.  
  
```  
const int FlagType;  /* Type specifier required */  
```  
  
 다음과 같이 표현하면 충분하지 않습니다.  
  
```  
const FlagType;      /* Incomplete specification */  
```  
  
 `FlagType`이 다시 선언되는 식별자가 아니라 형식의 일부로 간주되기 때문입니다. 이 선언은 다음과 같이 잘못된 선언으로 간주됩니다.  
  
```  
int;  /* Illegal declaration */  
```  
  
 포인터, 함수 및 배열 형식을 비롯한 모든 형식을 typedef를 사용하여 선언할 수 있습니다. 정의의 표시 유형이 선언의 표시 유형과 동일한 경우 구조체 또는 공용 구조체 형식을 정의하기 전에 구조체 또는 공용 구조체 형식에 대한 포인터의 typedef 이름을 선언할 수 있습니다.  
  
 typedef 이름을 사용하면 코드 가독성을 높일 수 있습니다. `signal`의 다음 세 가지 선언 모두 정확히 같은 형식을 지정하며, 첫 번째는 typedef 이름을 사용하지 않습니다.  
  
```  
typedef void fv( int ), (*pfv)( int );  /* typedef declarations */  
  
void ( *signal( int, void (*) (int)) ) ( int );  
fv *signal( int, fv * );   /* Uses typedef type */  
pfv signal( int, pfv );    /* Uses typedef type */  
```  
  
## <a name="examples"></a>예제  
 다음 예제에서는 typedef 선언을 보여 줍니다.  
  
```  
typedef int WHOLE; /* Declares WHOLE to be a synonym for int */  
```  
  
 `WHOLE`은 이제 `WHOLE i;` 또는 `const WHOLE i;`와 같은 변수 선언에서 사용할 수 있습니다. 하지만 `long WHOLE i;` 선언은 유효하지 않습니다.  
  
```  
typedef struct club   
{  
    char name[30];  
    int size, year;  
} GROUP;  
```  
  
 이 문은 `GROUP`을 세 멤버가 포함된 구조체 형식으로 선언합니다. 구조체 태그 `club`도 지정되어 있으므로 typedef 이름(`GROUP`) 또는 구조체 태그를 선언에서 사용할 수 있습니다. 태그와 함께 구조체 키워드를 사용해야 하며, typedef 이름과 함께 구조체 키워드를 사용할 수는 없습니다.  
  
```  
typedef GROUP *PG; /* Uses the previous typedef name   
                      to declare a pointer            */  
```  
  
 `PG` 형식은 `GROUP` 형식에 대한 포인터로 선언되며, 이는 다시 구조체 형식으로 정의됩니다.  
  
```  
typedef void DRAWF( int, int );  
```  
  
 이 예제에서는 값을 반환하지 않고 두 개의 int 인수를 사용하는 함수에 대한 `DRAWF` 형식을 제공합니다. 이는 예를 들어 다음 선언이  
  
```  
DRAWF box;   
```  
  
 다음 선언과 같음을 의미합니다.  
  
```  
void box( int, int );  
```  
  
## <a name="see-also"></a>참고 항목  



