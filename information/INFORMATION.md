# INFORMACION
A continuacion se detallan una serie de puntos a tomar en cuenta para una correcto estandar o informacion relevante en el apartado de INFORMACION para Angular.

# Sobre la creacion de modulos, servicios y modulos
Para crear un modulo se recomienda utilizar el siguiente comando
```
ng g m nameModule --routing
```

Modo largo
```
ng generate mmodule nameModule --routing
```

Para generar un servicio se utiliza el siguiente comando
```
ng g s nameService --skip-Tests=true
```
Modo largo
```
ng generate service nameService --skip-Tests=true
```

Y para generar los componentes
```
ng g c nameComponent --skip-Tests=true -v=None
```
Modo largo
```
ng generate component nameComponent --skip-Tests=true -v=None
```


### Localizacion
Evite usar sentencias para el texto de un mismo boton. Por obligacion se recomienda si existe 1 boton reutilizado con distinto texto crear 2 y con una sentencia que evite que se visualize el otro.


```html
// Manera correcta
<button mat-raised-button *ngIf="mode=='edit'" class="pull-right btn button-primary" color="primary" ngbTooltip="Editar"  (click)="submit()" [disabled]="!formLimit.valid" i18n="@@AdministratorLimitBUTTONOne">Editar</button>

<button mat-raised-button *ngIf="mode!='edit'" class="pull-right btn button-primary" color="primary" ngbTooltip="Agregar"
(click)="submit()" [disabled]="!formLimit.valid" i18n="@@AdministratorLimitBUTTONTwo">Agregar</button>
```

```html
// Manera incorrecta
<button mat-raised-button class="pull-right btn button-primary" color="primary" ngbTooltip="Agregar" (click)="submit()" [disabled]="!formLimit.valid">{mode=='edit'?"Editar":"Agregar"}}</button>
```