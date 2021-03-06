---
title: "ポインターへの参照 |Microsoft ドキュメント"
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
- references, to pointers
ms.assetid: 4ce48b08-1511-4d2f-a31f-95f99eac0c70
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3565c0f720d6f454fa53a2b3e8373c2b53f926ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="references-to-pointers"></a>References to Pointers (ポインターへの参照)
ポインターへの参照は、オブジェクトへの参照とほぼ同じ方法で宣言できます。 ポインターへの参照を宣言すると、通常のポインターのように使用される変更可能な値が生成されます。  
  
## <a name="example"></a>例  
 次のコード例で、ポインターへのポインターとポインターへの参照の使用方法の相違点について説明します。  
  
 関数 `Add1` および `Add2` は、機能的に同等です (ただし、呼び出し方法が異なります)。 違いは、`Add1` が二重の間接参照を使用しているのに対し、`Add2` はポインターへの参照を便利に利用している点です。  
  
```  
// references_to_pointers.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
  
// C++ Standard Library namespace  
using namespace std;  
  
enum {  
   sizeOfBuffer = 132  
};  
  
// Define a binary tree structure.  
struct BTree {  
   char  *szText;  
   BTree *Left;  
   BTree *Right;  
};  
  
// Define a pointer to the root of the tree.  
BTree *btRoot = 0;  
  
int Add1( BTree **Root, char *szToAdd );  
int Add2( BTree*& Root, char *szToAdd );  
void PrintTree( BTree* btRoot );  
  
int main( int argc, char *argv[] ) {  
   // Usage message  
   if( argc < 2 ) {  
      cerr << "Usage: Refptr [1 | 2]" << "\n";  
      cerr << "\nwhere:\n";  
      cerr << "1 uses double indirection\n";  
      cerr << "2 uses a reference to a pointer.\n";  
      cerr << "\nInput is from stdin.\n";  
      return 1;  
   }  
  
   char *szBuf = new char[sizeOfBuffer];  
   if (szBuf == NULL) {  
      cerr << "Out of memory!\n";  
      return -1;  
   }  
  
   // Read a text file from the standard input device and  
   //  build a binary tree.  
   //while( !cin.eof() )   
   {  
      cin.get( szBuf, sizeOfBuffer, '\n' );  
      cin.get();  
  
      if ( strlen( szBuf ) ) {  
         switch ( *argv[1] ) {  
            // Method 1: Use double indirection.  
            case '1':  
               Add1( &btRoot, szBuf );  
               break;  
            // Method 2: Use reference to a pointer.  
            case '2':  
               Add2( btRoot, szBuf );  
               break;  
            default:  
               cerr << "Illegal value '"  
                  << *argv[1]  
                  << "' supplied for add method.\n"  
                     << "Choose 1 or 2.\n";  
               return -1;  
         }  
      }  
   }  
   // Display the sorted list.  
   PrintTree( btRoot );  
}  
  
// PrintTree: Display the binary tree in order.  
void PrintTree( BTree* MybtRoot ) {  
   // Traverse the left branch of the tree recursively.  
   if ( btRoot->Left )  
      PrintTree( btRoot->Left );  
  
   // Print the current node.  
   cout << btRoot->szText << "\n";  
  
   // Traverse the right branch of the tree recursively.  
   if ( btRoot->Right )  
      PrintTree( btRoot->Right );  
}  
  
// Add1: Add a node to the binary tree.  
//       Uses double indirection.  
int Add1( BTree **Root, char *szToAdd ) {  
   if ( (*Root) == 0 ) {  
      (*Root) = new BTree;  
      (*Root)->Left = 0;  
      (*Root)->Right = 0;  
      (*Root)->szText = new char[strlen( szToAdd ) + 1];  
      strcpy_s((*Root)->szText, (strlen( szToAdd ) + 1), szToAdd );  
      return 1;  
   }  
   else {  
      if ( strcmp( (*Root)->szText, szToAdd ) > 0 )  
         return Add1( &((*Root)->Left), szToAdd );  
      else  
         return Add1( &((*Root)->Right), szToAdd );  
   }  
}  
  
// Add2: Add a node to the binary tree.  
//       Uses reference to pointer  
int Add2( BTree*& Root, char *szToAdd ) {  
   if ( Root == 0 ) {  
      Root = new BTree;  
      Root->Left = 0;  
      Root->Right = 0;  
      Root->szText = new char[strlen( szToAdd ) + 1];  
      strcpy_s( Root->szText, (strlen( szToAdd ) + 1), szToAdd );  
      return 1;  
   }  
   else {  
      if ( strcmp( Root->szText, szToAdd ) > 0 )  
         return Add2( Root->Left, szToAdd );  
      else  
         return Add2( Root->Right, szToAdd );  
   }  
}  
```  
  
```Output  
Usage: Refptr [1 | 2]  
  
where:  
1 uses double indirection  
2 uses a reference to a pointer.  
  
Input is from stdin.  
```  
  
## <a name="see-also"></a>参照  
 [参照](../cpp/references-cpp.md)