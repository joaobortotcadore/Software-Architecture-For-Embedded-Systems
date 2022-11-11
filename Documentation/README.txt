
/**
  ******************************************************************************
  * @Company    : Eder Andrade Ltda. 
  * @file       : README.txt
  * @author     : Eder Andrade
  * @date       : 18/02/2021
  * @brief      : First step to FOLLOW before put the hands on the code.
  ******************************************************************************
*/

********************************************************************************
                          SOFTWARE ARCHITECTURE DESIGN
********************************************************************************

Below, is showed how this software project is designed:
            
	 __________________________________________________________________         
	/                                                                  \
	|                      APPLICATION LAYER                           |
	|                                                                  |
	\__________________________________________________________________/   
	 __________________________________________________________________
	/                                                                  \
	|          APIs (Application Programming Interfaces) LAYER         |
	|                                                                  |
	\__________________________________________________________________/
	 __________________________________________________________________            
	/                                                                  \
	|                        DRIVERS LAYER                             |
	|                                                                  |
	\__________________________________________________________________/           
	 __________________________________________________________________            
	/                                                                  \
	|           HAL (Hardware Access Layer - microcontroller)          |
	|                                                                  |
	\__________________________________________________________________/ 


WHAT YOU, DEVELOPER, MUST KNOW:

    -> All these layer you are seing was thought to be independent, so take some
    minutes to understand how higher layer is calling the lower one;
    
    -> The relationship between the layers is made by FUNCTIONS / ROUTINES, foll
    owing what was said above and excluding the need to implement global or 
    extern variables types;
    
    -> If the developer needs change some configuration of hardware (peripheral)
    or include other funcionality, you should do it through HAL layer. Because
    it take cares all about files and routines created;
    
    -> The MAIN IDEA of this architecture is: the application layer just calls
    APIs functions, APIs layer just calls DRIVERS functions and this one, calls
    HAL functions. DO NOT JUMP ANY LAYER !
    
--------------------------------------------------------------------------------

1. FILES -----------------------------------------------------------------------

    ->  If you need create a file for the driver that this project doesn't 
        contains, please consider the name of file both .c and .h:
        >>> "company_name_drv_PERIPHREAL.c and same name for ".h".
        
    ->  If you need create a file for the API that this project doesn't contains,
        please consider the name of file both .c and .h:
        >>> "company_name_api_FUNCTION.c and same name for ".h".
        
2. NOTATION --------------------------------------------------------------------

    ->  Notation system is based on "Hungarian Notation", so the follow rules 
        MUST be follwed to easy understand the code:
        
        TYPE ===================================================================
        >> Variable of CHAR type            : cVarName  
        >> Variable of UNSIGNED CHAR type   : ucVarName 
        >> Variable of INT type             : iVarName
        >> Variable of UNSIGNED INT type    : uiVarName
        >> Variable of FLOAT type           : fVarName
        
        POINTER ================================================================
        >> Pointer of VOID type             : *pvVarName
        >> Pointer of CHAR type             : *pcVarName  
        >> Pointer of UNSIGNED CHAR type    : *pucVarName 
        >> Pointer of INT type              : *piVarName
        >> Pointer of UNSIGNED INT type     : *puiVarName
        >> Pointer of FLOAT type            : *pfVarName
        >> Pointer of struct type           : *pstVarName
        
        *** It is easy to understand that all variables starts its name with the
        letters of type it is related and if yours variables has more than one 
        name, then it has to follow:
        
        >> (type)(First Name)(Second Name) = tVariableName
        
        *** First letter of each variable name must be in uppercase with no spaces
        and underscore.
        
        TYPEDEF OF STRUTC ======================================================
        typedef struct
        {
            char    cVar;
            int     iVar;
            float   fVar;
            
        }st_name_you_choose_t;
        
        *** Starting the name with "st" indicating struct and finishing with "t".
        
        TYPEDEF OF ENUM ========================================================
        typedef enum
        {
            eNAME1 = 0  ,
            eNAME2      ,
            eNAME3      ,
            
        }e_name_you_choose_t;
        
        *** Starting the name with "e" indicating enum and finishing with "t". 
        
        FUNCTION ===============================================================
        >> "name_of_your_function()"
        
        *** All words in lowercase and separated by underscore.
        
3. DOCUMENTATION ---------------------------------------------------------------        

    -> Each file, don't matter if it is driver, API, ".c" or ".h" has to have a
    header as follow:
    
/**
  ******************************************************************************
  * @Company    : Name of company
  * @file       : name_of_file.c or .h
  * @author     : Name of author
  * @version	: version of driver, API or application files 
  * @date       : Data of the file was created
  * @brief      : What this file does
  ******************************************************************************
*/       
    -> If it is a ".c" file:
    
/* Includes ------------------------------------------------------------------*/ 
// C language standard library
// Alpe driver library
// Application

/*******************************************************************************
                            HOW TO USE THIS DRIVER
********************************************************************************

1. 	First, you should include in your .c file: "name_of_driver.h" and call OBJECT object,
	after that, you can use the follow resources of the driver

	- OBJECT: this is the object that will control the peripheral;	

	Data -----------------------------------------------------------------------

	- OBJECT.Variables ========> What it stores. 	

	Methods --------------------------------------------------------------------

	- OBJECT.Methods() ========> What it does.

*******************************************************************************/

/* Private define ------------------------------------------------------------*/
/* Private macros ------------------------------------------------------------*/
/* Private typedef -----------------------------------------------------------*/
/* Private variables ---------------------------------------------------------*/
/* Private function prototypes -----------------------------------------------*/    
/* Public objects ------------------------------------------------------------*/
/* Bodies of private functions -----------------------------------------------*/

	-> This is the brief every function must have
/**
  * @Func       : name of function    
  * @brief      : Put your description here
  * @pre-cond.  : Conditions needed to APIs/drivers work
  * @post-cond. : Conditions achieved after API/drivers executed
  * @parameters : Fill this field wherever there is or not parameter / returning
  * @retval     : Fill this field wherever there is or not parameter / returning
  */

/*****************************END OF FILE**************************************/

    -> If it is a ".h" file:
    
/* Includes ------------------------------------------------------------------*/       
/* Define --------------------------------------------------------------------*/
/* Typedef -------------------------------------------------------------------*/
/* Public objects ------------------------------------------------------------*/
/*****************************END OF FILE**************************************/
    
    
        
        
