# Reproduction workflow and review checklist

## MATLAB

1. Keep the original files unchanged and work on copies.
2. Open `matlab/state1.mlx` for the first cavity position, or `matlab/allstates.mlx` for all sixteen positions.
3. The `.m` files are extracted code alternatives, not corrected implementations. Set MATLAB's Current Folder to `matlab/` before using them.
4. Inspect `Vis` for temperatures and `allst` for stored temperature arrays in the multi-position script.
5. Review the heat-rate calculation before interpreting `q`, `Qall`, or `maxq`.

The source converts the solved temperatures to Celsius but subtracts ambient temperatures still expressed in kelvin in many heat-rate terms. Corner terms are inconsistent as well. Use a single consistent scale for every temperature difference in any corrected revision. The original scripts are retained unchanged.

The sum covers convection on three outer sides but does not include conductive heat exchange at the prescribed-temperature left wall. Decide which boundary set and sign convention define the objective, then check a complete energy balance.

`maxq=min(Qall)` selects the most negative indicator. This is not automatically the largest outward heat rate. Re-evaluate the cavity selection after correcting units and defining the objective. A coarse sixteen-position search does not prove a continuous global optimum.

## COMSOL

1. Open working copies of the supplied MPH files in a compatible COMSOL installation.
2. Preserve `Original(DONT TOUCH).mph` as the original baseline.
3. Verify square dimensions, cavity position, material conductivity, fixed-temperature boundaries, convection coefficients, and ambient temperatures.
4. Check the out-of-plane depth and unit conventions.
5. Inspect the mesh and solved study before comparing temperatures.
6. Inspect the selected boundaries and whether heat flux is evaluated by line integration or a point summation. Normal heat flux is not itself a total heat rate.
7. Compare results using the same sign convention and boundary set as MATLAB.

The source quotes 17292 W in its State 1 prose but -18.123 kW in the final table. Reconcile those values with saved model evaluations. The source also alternates between State 3 and State 4 in its comparison description. The archive contains eleven MPH files rather than sixteen complete numbered state models.

`ChimHTdata.St1.txt` and `ChimHTdata.St1.xlsx` are retained unchanged. The English report also contains the source report's full coordinate/temperature table; it should not be assumed to have identical precision or sampling to the separate exports.

## Additional source code

The archive already contains both MATLAB Live Scripts. Add any separately stored helpers or revised scripts under `matlab/`, documenting their inputs, version, purpose, and verified execution instructions. Keep corrections identifiable and distinguish newly computed results from the historical report.

No MATLAB execution or native COMSOL recomputation was performed during this preparation. The LaTeX compilation and file-integrity checks do not validate the thermal model.
