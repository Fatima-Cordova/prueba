# INFORMACION
A continuacion se detallan una serie de puntos a tomar en cuenta para una correcto estandar en el apartado de INFORMACION para Angular.


### Localizacion
Evite usar sentencias para el texto de un mismo boton. Por obligacion se recomienda si existe 1 boton reutilizado con distinto texto crear 2 y con una sentencia que evite que se visualize el otro.


```html
// Manera correcta
<button mat-raised-button *ngIf="mode=='edit'" class="pull-right btn button-primary" color="primary" ngbTooltip="Editar"  (click)="submit()" [disabled]="!limitFrm.valid" i18n="@@AdministratorLimitBUTTONOne">Editar</button>

<button mat-raised-button *ngIf="mode!='edit'" class="pull-right btn button-primary" color="primary" ngbTooltip="Agregar"
(click)="submit()" [disabled]="!limitFrm.valid" i18n="@@AdministratorLimitBUTTONTwo">Agregar</button>
```

```html
// Manera incorrecta
<button mat-raised-button class="pull-right btn button-primary" color="primary" ngbTooltip="Agregar" (click)="submit()" [disabled]="!limitFrm.valid">{mode=='edit'?"Editar":"Agregar"}}</button>
```