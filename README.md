# transform-supercell-atom-position


A graphical tool for generating supercells.

## Features

This tool can expand original XYZ format unit cell files by specified multiples in three directions to create larger supercells.

## Usage

### Graphical Interface Mode (Recommended)

1. Double-click to run `test.exe`
2. Set the following parameters in the interface:
   - **Input File**: Select the original .xyz file
   - **Output File**: Set the save location for the generated supercell file
   - **Supercell Multiples**: Set the repetition counts for x, y, z directions (nx, ny, nz)
3. Click the "Generate Supercell" button
4. A success message will display the atom count change

### Command Line Mode

```bash
# Use default parameters (nx=2, ny=2, nz=1)
test.exe

# Specify input and output files
test.exe input.xyz output.xyz

# Specify supercell multiples
test.exe input.xyz output.xyz -nx 3 -ny 3 -nz 2
```

## Input File Format

The input file should be in XYZ format with two header lines:

```
Number of atoms
Lattice="a1_x a1_y a1_z a2_x a2_y a2_z a3_x a3_y a3_z"
Atom_type x_coordinate y_coordinate z_coordinate
Atom_type x_coordinate y_coordinate z_coordinate
...
```

### Example

```
2
Lattice="3.0 0.0 0.0 0.0 3.0 0.0 0.0 0.0 3.0"
O 0.0 0.0 0.0
H 1.5 1.5 1.5
```

## Parameters

- **nx**: Repetition count in x direction (default: 2)
- **ny**: Repetition count in y direction (default: 2)
- **nz**: Repetition count in z direction (default: 1)

Total atoms = Original atoms × nx × ny × nz

## Output File Format

The output file maintains the same XYZ format, containing all atom information of the supercell.

## Notes

- The input file must contain correct Lattice information
- Supercell multiples must be positive integers
- Ensure the input file path is correct
